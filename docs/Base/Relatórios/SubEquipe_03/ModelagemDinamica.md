# SubEquipe_03 — Modelagem Dinâmica na Notação UML

## Descrição

Modelagem do processo de negócio da SubEquipe_03, no escopo do **FOCO_02 — Modelagem Dinâmica na Notação UML**. O documento apresenta a modelagem dinâmica do software utilizando a notação UML, buscando representar o comportamento do sistema e a interação entre seus principais elementos ao longo da execução dos processos.

## Objetivo

Elaborar uma modelagem dinâmica em UML para o sistema desenvolvido pela equipe, evidenciando o comportamento dos processos, as atividades realizadas, os eventos, as interações e os pontos de decisão envolvidos na execução das funcionalidades do sistema.

## Metodologia

A modelagem dinâmica foi elaborada a partir da análise dos processos e das funcionalidades do sistema, buscando representar o comportamento da aplicação e a sequência de eventos envolvidos em sua execução.

O processo envolveu a identificação dos principais fluxos e interações do sistema, considerando as ações realizadas pelos usuários e as respostas produzidas pela aplicação. A partir dessa análise, foram definidos os elementos necessários para representar o comportamento do processo utilizando a notação UML.

A elaboração do modelo foi realizada de forma colaborativa pelos integrantes da SubEquipe_03, utilizando as ferramentas adotadas pela equipe para construção e documentação dos diagramas.

As decisões de modelagem foram fundamentadas nos conceitos da UML e na literatura de Engenharia de Software, buscando representar de maneira clara e consistente o comportamento do sistema.

## Escolha da Modelagem

A estratégia adotada utiliza diagramas comportamentais complementares, de modo que cada um responda a uma pergunta distinta sobre a Página da postagem:

1. **Diagrama de Casos de Uso:** delimita a fronteira da funcionalidade, identificando os atores envolvidos e os serviços que a página oferece a cada um deles. Responde *"o que o sistema faz e para quem"*.
2. **Diagrama de Sequência:** detalha a ordem temporal das mensagens trocadas entre os objetos durante a execução de um fluxo específico. Responde *"em que ordem isso acontece"*.
3. **Diagrama de Comunicação:** apresenta a mesma interação sob ênfase estrutural, evidenciando os vínculos entre as instâncias que colaboram. Responde *"quem se conecta com quem"*.

A escolha conjunta do Diagrama de Sequência e do Diagrama de Comunicação é deliberada. Ambos são diagramas de interação e, segundo a especificação da UML 2.5.1 (OMG, 2017), expressam informação semanticamente equivalente, diferindo apenas na ênfase: o de sequência destaca a ordenação temporal, enquanto o de comunicação destaca a organização estrutural dos participantes. Apresentá-los lado a lado permite discutir criticamente essa equivalência e demonstrar domínio da notação, em vez de multiplicar diagramas sem propósito.

O Diagrama de Casos de Uso foi posicionado como ponto de entrada por cumprir a função de delimitar o escopo antes do detalhamento dos fluxos, conforme a abordagem descrita por Booch, Rumbaugh e Jacobson (2005).

## Modelagem Dinâmica

### 1. Diagrama de Casos de Uso

O Diagrama de Casos de Uso delimita a fronteira da **Página da postagem** e identifica os quatro atores que interagem com ela. O ator `Visitante` representa o usuário não autenticado, que dispõe apenas das operações de leitura e compartilhamento. O `Usuário Autenticado` o especializa, acrescentando as operações de escrita e de avaliação. Dele derivam ainda o `Autor do Conteúdo`, responsável pela edição e remoção do próprio conteúdo, e o `Moderador`, que pode remover conteúdo de terceiros.

Os relacionamentos `«include»` evidenciam que autenticar-se é condição obrigatória para todas as operações de escrita, ao passo que o relacionamento `«extend»` registra que denunciar um conteúdo é um comportamento opcional, acionado a partir da visualização da publicação. A generalização entre *Responder comentário* e *Publicar comentário* reflete a estrutura recursiva da árvore de comentários já representada no Diagrama de Classes: responder é publicar um comentário cujo conteúdo-pai é outro comentário.

```plantuml
@startuml
left to right direction
skinparam nodesep 45
skinparam ranksep 90
title Casos de Uso da Pagina da Postagem

actor "Visitante" as V
actor "Usuario Autenticado" as UA
actor "Autor do Conteudo" as AC
actor "Moderador" as MOD

UA --|> V
AC --|> UA
MOD --|> UA

rectangle "Pagina da Postagem" {
  usecase "Visualizar publicacao" as UC01
  usecase "Visualizar arvore\nde comentarios" as UC02
  usecase "Compartilhar publicacao" as UC03
  usecase "Publicar comentario" as UC04
  usecase "Responder comentario" as UC05
  usecase "Votar em conteudo\n(TabCoins)" as UC06
  usecase "Editar conteudo" as UC07
  usecase "Remover conteudo" as UC08
  usecase "Denunciar conteudo" as UC09
  usecase "Autenticar-se" as UC00
}

V --> UC01
V --> UC03
UA --> UC04
UA --> UC05
UA --> UC06
UA --> UC09
AC --> UC07
AC --> UC08
MOD --> UC08

UC01 ..> UC02 : <<include>>
UC04 ..> UC00 : <<include>>
UC06 ..> UC00 : <<include>>
UC07 ..> UC00 : <<include>>
UC08 ..> UC00 : <<include>>
UC09 ..> UC00 : <<include>>
UC05 --|> UC04
UC09 ..> UC01 : <<extend>>
@enduml
```

<p align="center">Figura 1: Diagrama de Casos de Uso da Página da postagem. Fonte: SubEquipe_03 (2026).</p>

### 2. Diagrama de Sequência

O Diagrama de Sequência detalha o fluxo de **publicação de um comentário**, desde a submissão do formulário até a atualização da árvore de comentários na interface. Foi escolhido por concentrar, em um único fluxo, os três elementos centrais da funcionalidade: a validação da entrada, o controle de acesso e a regra de negócio dos TabCoins.

O diagrama emprega dois fragmentos combinados do tipo `alt`. O primeiro separa a validação realizada no cliente, que evita uma requisição desnecessária quando o corpo do comentário é inválido. O segundo trata a verificação de sessão no servidor, retornando `403 Forbidden` quando a sessão é inválida ou expirada — o que caracteriza a validação em duas camadas adotada pela aplicação.

Observa-se ainda que a criação do comentário dispara o crédito de TabCoins ao autor, registrado como uma operação de saldo distinta da persistência do conteúdo. Essa separação é o que permite auditar o histórico de movimentações independentemente do conteúdo que as originou.

```plantuml
@startuml
title Publicacao de comentario na Pagina da Postagem

actor "Usuario autenticado" as U
boundary "PostPage\n(UI)" as UI
control "ContentsAPI\n/api/v1/contents" as API
control "AuthService" as AUTH
control "ContentService" as CS
entity "ContentRepository" as REPO
control "TabCoinsService" as TC
database "PostgreSQL" as DB

U -> UI : escreverComentario(corpo)
activate UI
UI -> UI : validarFormulario(corpo)

alt corpo invalido (vazio ou acima do limite)
  UI --> U : exibir mensagem de validacao
else corpo valido
  UI -> API : POST /contents {parent_id, body}
  activate API

  API -> AUTH : autenticar(sessionToken)
  activate AUTH
  AUTH -> DB : SELECT sessao WHERE token = ?
  DB --> AUTH : sessao
  AUTH --> API : usuario
  deactivate AUTH

  alt sessao invalida ou expirada
    API --> UI : 403 Forbidden
    deactivate API
    UI --> U : solicitar autenticacao
  else sessao valida
    activate API
    API -> CS : criarComentario(usuario, parentId, corpo)
    activate CS

    CS -> REPO : buscarConteudoPai(parentId)
    activate REPO
    REPO -> DB : SELECT conteudo WHERE id = ?
    DB --> REPO : conteudoPai
    REPO --> CS : conteudoPai
    deactivate REPO

    CS -> CS : sanitizarMarkdown(corpo)

    CS -> REPO : salvar(comentario)
    activate REPO
    REPO -> DB : INSERT INTO contents
    DB --> REPO : comentario persistido
    REPO --> CS : comentario
    deactivate REPO

    CS -> TC : creditarPorPublicacao(usuario, comentario)
    activate TC
    TC -> DB : INSERT INTO balance_operations
    DB --> TC : saldo atualizado
    TC --> CS : tabCoinsCreditados
    deactivate TC

    CS --> API : comentario
    deactivate CS
    API --> UI : 201 Created {comentario}
    deactivate API

    UI -> UI : inserirNaArvoreDeComentarios(comentario)
    UI --> U : exibir comentario publicado
  end
end
deactivate UI
@enduml
```

<p align="center">Figura 2: Diagrama de Sequência — publicação de comentário. Fonte: SubEquipe_03 (2026).</p>

### 3. Diagrama de Comunicação

O Diagrama de Comunicação representa o fluxo de avaliação de um conteúdo (votação em TabCoins), evidenciando a colaboração e a troca de mensagens entre os objetos participantes.

<!-- ESPAÇO RESERVADO PARA O DIAGRAMA DE COMUNICAÇÃO
     Artefato elaborado na branch `docs/sub03-dinamico`.
     Ao integrar a branch, substituir este comentário por:

<div align="center">
<img src="Base/images/SubEquipe_03/diagrama-comunicacao.png" alt="Diagrama de Comunicação do fluxo de avaliação" width="800">
</div>

<p align="center">Figura 3: Diagrama de Comunicação — avaliação de conteúdo. Fonte: SubEquipe_03 (2026).</p>
-->

### 4. Diagrama de Estados

```plantuml
@startuml
title Ciclo de Vida do Conteúdo na Página da Postagem

skinparam nodesep 30
skinparam ranksep 55

state "Rascunho" as Rascunho
state "Publicado" as Publicado
state "Em revisão" as EmRevisao
state "Removido" as Removido

[*] -down-> Rascunho : criar publicação
Rascunho -down-> Publicado : publicar [corpo válido] /\nregistrar publicação, creditar autor
[*] -down-> Publicado : comentar [usuário autenticado] /\nregistrar publicação, creditar autor

Publicado -down-> EmRevisao : denunciar [suspeita de abuso] /\ndebitar créditos
EmRevisao -up-> Publicado : aprovar [moderador] /\nrestaurar créditos

Publicado -down-> Removido : remover [autor ou moderador] /\ndebitar créditos
EmRevisao -down-> Removido : confirmar remoção [moderador]
Rascunho -down-> Removido : remover [autor]

Removido -down-> [*]

note right of Publicado
  Único estado visível na Página da postagem.
  Comentar e avaliar exigem este estado.
end note

note right of Removido
  Transições bloqueadas:
  Publicado não retorna a Rascunho.
  Removido é final e não aceita alteração.
end note
@enduml
```

<p align="center">Figura 4: Diagrama de Estados — ciclo de vida do conteúdo. Fonte: SubEquipe_03 (2026).</p>

## Referências

BOOCH, Grady; RUMBAUGH, James; JACOBSON, Ivar. **UML: Guia do Usuário**. 2. ed. Rio de Janeiro: Elsevier, 2005.

FOWLER, Martin. **UML Essencial: um breve guia para a linguagem-padrão de modelagem de objetos**. 3. ed. Porto Alegre: Bookman, 2005.

OBJECT MANAGEMENT GROUP. **OMG Unified Modeling Language (OMG UML), Version 2.5.1**. 2017. Disponível em: [https://www.omg.org/spec/UML/2.5.1/PDF](https://www.omg.org/spec/UML/2.5.1/PDF). Acesso em: 17 set. 2026.

UML-DIAGRAMS.ORG. **UML Sequence Diagrams**. Disponível em: [https://www.uml-diagrams.org/sequence-diagrams.html](https://www.uml-diagrams.org/sequence-diagrams.html). Acesso em: 17 set. 2026.

UML-DIAGRAMS.ORG. **UML Use Case Diagrams**. Disponível em: [https://www.uml-diagrams.org/use-case-diagrams.html](https://www.uml-diagrams.org/use-case-diagrams.html). Acesso em: 17 set. 2026.

## Nível de Contribuição dos Integrantes

| Nome | % de Contribuição |
|:---|:---:|
| [Caio Alexandre](https://github.com/bitterteriyaki) | 30% |
| [Guilherme Moura](https://github.com/Guilherme-Moura) | |
| [Leonardo Fachinello Bonetti](https://github.com/LeoFacB) | |
| [Pablo Rodrigues Lima](https://github.com/Pablo-R-L) | |

<p align="center">Tabela 1: Contribuição dos integrantes.</p>

## Histórico de Versões

| Versão | Data | Descrição | Autor(es) | Revisor(es) | Detalhe da Revisão |
|:------:|:----:|:----------|:----------|:------------|:-------------------|
| 1.0 | 13/09/2026 | Criação do documento de Modelagem Dinâmica na Notação UML da SubEquipe_03. | [Arthur Fernandes](https://github.com/arthurfernandesj)  |  | Criação da estrutura inicial do documento e preparação para inserção da modelagem dinâmica. |
| 1.1 | 17/09/2026 | Adição do Diagrama de Casos de Uso e do Diagrama de Sequência da Página da postagem. | [Caio Alexandre](https://github.com/bitterteriyaki) | [Arthur Fernandes](https://github.com/arthurfernandesj) | Elaboração dos dois diagramas em PlantUML, definição da seção Escolha da Modelagem com a justificativa da complementaridade entre os diagramas de interação e inclusão das referências bibliográficas. |

<p align="center">Tabela 2: Histórico de Versões.</p>

Ver também: [Modelagem Estática na Notação UML](ModelagemEstatica.md) · [IA Generativa](IAGenerativa.md)