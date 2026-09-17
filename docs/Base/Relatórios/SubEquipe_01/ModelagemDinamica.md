# SubEquipe_01 — Modelagem Dinâmica na Notação UML

## Descrição

Modelagem do processo de negócio da SubEquipe_01, no escopo do **FOCO_02 — Modelagem Dinâmica na Notação UML**. O documento apresenta a modelagem dinâmica do software utilizando a notação UML, buscando representar o comportamento do sistema e a interação entre seus principais elementos ao longo da execução dos processos.

## Objetivo

Elaborar uma modelagem dinâmica em UML para o sistema desenvolvido pela equipe, evidenciando o comportamento dos processos, as atividades realizadas, os eventos, as interações e os pontos de decisão envolvidos na execução das funcionalidades do sistema.

## Metodologia

A modelagem dinâmica foi elaborada a partir da análise dos processos e das funcionalidades do sistema, buscando representar o comportamento da aplicação e a sequência de eventos envolvidos em sua execução.

O processo envolveu a identificação dos principais fluxos e interações do sistema, considerando as ações realizadas pelos usuários e as respostas produzidas pela aplicação. A partir dessa análise, foram definidos os elementos necessários para representar o comportamento do processo utilizando a notação UML.

A elaboração do modelo foi realizada de forma colaborativa pelos integrantes da SubEquipe_01, utilizando as ferramentas adotadas pela equipe para construção e documentação dos diagramas.

As decisões de modelagem foram fundamentadas nos conceitos da UML e na literatura de Engenharia de Software, buscando representar de maneira clara e consistente o comportamento do sistema.


## Diagrama de Estados

O diagrama mapeia o ciclo de vida do processo de entrada de usuários na plataforma TabNews, detalhando a dinâmica de navegação entre o acesso inicial e a navegação autenticada.

A jornada se origina no ponto de entrada do sistema, que conduz a interface para a etapa de seleção de acesso. Uma ramificação condicional avalia se o visitante já possui cadastro prévio:

* **Usuários sem cadastro:**
 O sistema direciona o fluxo para o bloco interno de registro, onde ocorre a coleta das credenciais (e-mail, nome de usuário e senha). Havendo a validação dos parâmetros e a confirmação do endereço de e-mail, o fluxo é reaproveitado e convergido para a etapa de acesso.

* **Usuários já cadastrados:**
 O fluxo avança diretamente para a submissão das credenciais de login. O sistema processa os dados inseridos e, em caso de conformidade, autoriza o acesso do perfil, redirecionando o usuário à página inicial e encerrando o ciclo no estado de sucesso.

A representação utiliza a convenção gráfica da UML para diagramação de estados, empregando pseudoestado de início, retângulos para estados simples e compostos, losangos de verificação e o estado final de conclusão. O modelo foi construído conforme as diretrizes teóricas de modelagem do projeto.

### Modelagem Dinâmica


<div align="center">
  <img src="Base/images/diagrama_estados.png" alt="Diagrama de estados" width="800">
  
  <p><strong>Figura 2:</strong> Diagrama de Estados — Login e Autenticação. Fonte: SubEquipe_01 (2026).</p>
</div>

O estado composto de cadastro centraliza todo o fluxo iterativo de registro: as etapas internas de coleta das credenciais, verificação dos parâmetros e confirmação do endereço de e-mail alternam-se caso ocorra alguma inconsistência nos dados, sem que essas validações intermediárias poluam o nível principal da aplicação. 

Ao sair da etapa de autenticação, a transição guardada pela verificação de credenciais determina se o usuário é redirecionado com sucesso para a tela inicial (Home) ou se permanece retido na tentativa de acesso até a correção dos dados, garantindo que o ciclo só avance ao atingir o estado final de acesso autorizado.

## Referências

<p>
  UNB FCTE — ARQDSW. Módulo de Modelagem. Disponível em: 
  <a href="https://sites.google.com/view/unb-fcte-arqdsw/m%C3%B3dulos/m%C3%B3dulo-modelagem?authuser=0" target="_blank" rel="noopener noreferrer">
    https://sites.google.com/view/unb-fcte-arqdsw/módulos/módulo-modelagem
  </a>. 
  <small>Acesso em: 15 set. 2026.</small>
</p>

## Nível de Contribuição dos Integrantes

| Nome | % de Contribuição |
|:---|:---:|
| [Arthur Fernandes](https://github.com/arthurfernandesj) | 33,3% |
| [Giovana Fontes](https://github.com/GiovanaFontesS) | 33,3% |

<p align="center">Tabela 1: Contribuição dos integrantes.</p>

## Histórico de Versões

| Versão | Data | Descrição | Autor(es) | Revisor(es) | Detalhe da Revisão |
|:------:|:----:|:----------|:----------|:------------|:-------------------|
| 1.0 | 13/09/2026 | Criação do documento de Modelagem Dinâmica na Notação UML da SubEquipe_01. | [Arthur Fernandes](https://github.com/arthurfernandesj)  |  | Criação da estrutura inicial do documento e preparação para inserção da modelagem dinâmica. |
| 1.1 | 17/09/2026 | Criação do documento de Modelagem Dinâmica na Notação UML da SubEquipe_01. | [Giovana Fontes](https://github.com/GiovanaFontesS)  |  | Modelagem Dinamica, introdução e desenvolvimento |

<p align="center">Tabela 2: Histórico de Versões.</p>

Ver também: [Modelagem Estática na Notação UML](ModelagemEstatica.md) · [IA Generativa](IAGenerativa.md)