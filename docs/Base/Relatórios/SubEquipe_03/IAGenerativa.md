# SubEquipe_03 — IA Generativa

## Descrição

Registro do **FOCO_03 — IA Generativa** da SubEquipe_03. O documento reúne os pontos de vista dos integrantes sobre as lições aprendidas durante a entrega e apresenta uma análise crítica sobre o uso de ferramentas de IA Generativa no desenvolvimento das atividades de modelagem.

## Objetivo

Registrar as experiências dos integrantes da SubEquipe_03 com o uso de IA Generativa durante a realização das atividades da entrega, destacando as principais lições aprendidas, as contribuições da ferramenta e as limitações identificadas ao longo do processo.

A análise busca evidenciar o uso consciente e crítico da IA Generativa, considerando a necessidade de validação das informações produzidas pela ferramenta com base nos conhecimentos adquiridos, na documentação do projeto e na literatura utilizada pela equipe.

**Todos os integrantes da SubEquipe_03 devem participar.**

## Metodologia

A coleta dos pontos de vista foi realizada de forma colaborativa entre os integrantes da SubEquipe_03, considerando as atividades desenvolvidas durante a entrega de Modelagem.

Cada integrante deve registrar suas principais lições aprendidas e descrever, de forma crítica, como a IA Generativa foi utilizada durante a realização das atividades. Quando utilizada, a ferramenta foi empregada como apoio à compreensão de conceitos, elaboração de ideias, revisão ou desenvolvimento das atividades, não substituindo a análise e a validação realizadas pelos integrantes da equipe.

As informações e sugestões obtidas por meio da IA Generativa foram analisadas e validadas pela equipe antes de serem incorporadas à documentação ou aos artefatos do projeto.

## Pontos de Vista dos Integrantes

### Caio Alexandre Ornelas Silva

**Lições aprendidas**

Não foram registradas lições aprendidas específicas por este integrante nesta entrega.

**Uso da IA Generativa e senso crítico**

A IA Generativa foi utilizada com a finalidade de acelerar o desenvolvimento do trabalho, reduzindo o tempo gasto na elaboração e na estruturação dos artefatos da entrega.

O uso concentrou-se na produção dos diagramas UML e da documentação associada, em que a ferramenta permitiu obter rapidamente uma primeira versão dos modelos, que em seguida foi ajustada ao escopo da Página da postagem e à nomenclatura já adotada pela equipe no Diagrama de Classes.

A ferramenta foi empregada também na automação das atividades de versionamento, abrangendo a organização das alterações em commits temáticos, a redação das mensagens de commit segundo o padrão já adotado pela equipe e a elaboração da descrição do *pull request*. Essa automação teve como objetivo reduzir o esforço operacional associado ao registro das contribuições e assegurar a consistência do histórico do repositório.

A validação dos artefatos permaneceu sob responsabilidade do integrante: os diagramas produzidos foram verificados quanto à sintaxe da notação e conferidos visualmente antes de serem incorporados à documentação, e o conteúdo de cada commit foi revisado antes de ser registrado.

### Guilherme Moura da Silva Neto

**Lições aprendidas**

Durante a elaboração da modelagem dinâmica, a principal lição aprendida foi o potencial da IA Generativa como facilitadora para contornar a curva de aprendizado de novas ferramentas tecnológicas. A utilização da IA para gerar a sintaxe do PlantUML provou-se consideravelmente mais ágil do que o estudo inicial da linguagem a partir do zero ou a busca exaustiva por templates. Contudo, a experiência evidenciou que a IA atua primordialmente como um acelerador de ponto de partida, sendo indispensável a intervenção e a revisão humana iterativa para refinar o diagrama e adequá-lo às especificidades lógicas do domínio modelado.

**Uso da IA Generativa e senso crítico**

A IA Generativa foi empregada de forma central na transcrição do fluxo modelado para o código PlantUML. Por não haver familiaridade prévia com a sintaxe da plataforma, solicitou-se à IA a geração de um esboço inicial dos Diagramas de Classes e de Comunicação. A partir desse modelo-base, aplicou-se o senso crítico para realizar o refinamento manual do código, corrigindo eventuais erros de sintaxe estrutural gerados pela ferramenta e ajustando as interações para refletir a regra de negócio analisada. Para fins de comparação e demonstração desse processo, um registro da versão inicial bruta gerada pela ferramenta foi incluído nas evidências, permitindo observar as modificações implementadas até o resultado final.

Adicionalmente, a IA foi utilizada como suporte para a formatação e organização da documentação técnica da página. A ferramenta auxiliou na estruturação dos tópicos e na padronização textual.

### Leonardo Fachinello Bonetti

**Lições aprendidas**

A principal lição aprendida foi que a utilidade da IA Generativa depende menos da qualidade do texto que ela produz e mais das restrições impostas a ela antes de produzir. Ao exigir que toda afirmação sobre o sistema tomado como referência viesse acompanhada de arquivo e linha, o que era plausível passou a ser verificável, e a diferença ficou evidente: uma parte do que a ferramenta havia proposto inicialmente não resistiu à conferência no código-fonte.

O caso mais claro foi o estereótipo `«JDBC»` na comunicação com o banco de dados, repetido do Diagrama de Componentes. A conferência no repositório de referência mostrou que a conexão é feita por um driver JavaScript sobre o protocolo nativo do PostgreSQL, e não por JDBC, que é uma API da plataforma Java. A decisão foi não replicar o estereótipo no Diagrama de Implantação e registrar a divergência, em vez de propagar um erro por consistência aparente entre artefatos.

A segunda lição foi sobre escopo. A IA tende a produzir mais do que o necessário quando não é contida: uma tabela de decisões de modelagem com vinte linhas foi gerada e depois removida, por repetir em formato tabular aquilo que o diagrama e o texto já diziam. O conteúdo que de fato justificava existir, as adaptações e as omissões deliberadas, foi reescrito como texto corrido. Avaliar criticamente o excesso mostrou-se tão necessário quanto avaliar o erro.

A terceira lição diz respeito ao resultado visual. O código PlantUML gerado estava sintaticamente correto desde a primeira versão, mas o diagrama resultante era largo e com arestas cruzadas, ilegível na página. Foram necessárias várias iterações de disposição até chegar a um layout adequado, o que evidencia que correção sintática e qualidade de comunicação são critérios distintos, e que apenas o segundo pode ser avaliado por inspeção do artefato renderizado.

**Uso da IA Generativa e senso crítico**

A ferramenta utilizada foi o Claude, por meio do Claude Code, em três frentes: análise do repositório tomado como referência, elaboração dos diagramas em PlantUML e redação da documentação associada.

Na análise, a ferramenta percorreu o código do sistema de referência para levantar o comportamento que seria modelado — a geração da página da publicação, a organização das rotas da API, a conexão com o banco de dados, o envio de notificação por e-mail e o ciclo de vida do conteúdo. O levantamento foi conduzido sob a exigência de que cada afirmação fosse acompanhada da localização exata no código, o que permitiu conferir individualmente as referências antes de incorporá-las ao documento.

Na elaboração dos diagramas, a ferramenta produziu o código PlantUML do Diagrama de Implantação (FOCO_01) e do Diagrama de Estados (FOCO_02) a partir da estrutura e das decisões definidas previamente: quais nós representar, quais componentes do Diagrama de Componentes deveriam ser manifestados por cada artefato e quais estados o Fórum precisaria de fato. Os diagramas foram renderizados e inspecionados visualmente a cada etapa, e o resultado final é fruto de sucessivas correções de disposição.

O senso crítico foi exercido nas decisões que a ferramenta não tomou: a definição do escopo de cada diagrama, a recusa do estereótipo incorreto herdado do Diagrama de Componentes, a escolha de nomes de estado em português sem termo técnico ou de marca, a omissão deliberada de transições e de elementos fora do escopo da Página da postagem, a remoção da tabela de decisões por desproporção e a decisão de manter os diagramas como blocos PlantUML integrados ao Markdown, seguindo a convenção já adotada pela subequipe, em vez de imagens exportadas.

## Análise Crítica do Uso de IA Generativa

Os três integrantes recorreram à IA Generativa com o mesmo propósito: obter rapidamente uma primeira versão dos artefatos e, a partir dela, trabalhar. Nenhum aproveitou o resultado como veio. Caio Alexandre ajustou os modelos gerados ao escopo da Página da postagem e à nomenclatura já adotada no Diagrama de Classes; Guilherme Moura refinou manualmente o código recebido, corrigindo erros de sintaxe e adequando as interações à regra de negócio analisada; Leonardo Bonetti refez a disposição dos diagramas várias vezes até que ficassem legíveis na página. O que a ferramenta entregou, nos três casos, foi um ponto de partida.

O uso se concentrou na produção de código PlantUML, e a razão ficou explícita no relato de Guilherme Moura: ninguém dominava a sintaxe da notação. A IA entrou onde a dificuldade era de linguagem de marcação, não de modelagem. Decidir o que representar, em que nível de abstração e com qual recorte continuou sendo trabalho dos integrantes, e vale deixar essa fronteira clara no registro.

Ao comparar as experiências, a equipe percebeu que cada um havia validado o resultado de um jeito diferente, e que os três jeitos não se equivalem. Caio conferiu a sintaxe e olhou o diagrama renderizado antes de incorporá-lo ao documento. Guilherme foi além e checou se as interações representadas correspondiam à regra de negócio, guardando a versão bruta inicial como evidência do que precisou mudar. Leonardo confrontou cada afirmação com o código do sistema tomado como referência, exigindo arquivo e linha. Os três níveis se somam, e só o último alcança o erro mais incômodo: a afirmação que parece certa e não é.

Houve ainda um caso em que a ferramenta preferiu a coerência entre artefatos à coerência com a realidade. Ao elaborar o Diagrama de Implantação, ela repetiu o estereótipo `«JDBC»` que estava no Diagrama de Componentes — só que o sistema analisado não usa JDBC, e sim um driver JavaScript sobre o protocolo nativo do PostgreSQL. A IA tende a se harmonizar com o material que recebe, o que ajuda quando se trata de vocabulário e atrapalha quando se trata de fato. Separar uma coisa da outra exigiu ir conferir fora dela.

Outra coisa que a equipe notou é que a ferramenta entrega mais do que se pede. Uma tabela de decisões de modelagem com vinte linhas foi gerada e depois retirada do documento de Modelagem Dinâmica, porque repetia em formato tabular o que o diagrama e o texto já diziam. Dessa vez não havia erro algum a corrigir: o que faltava era senso de proporção, e esse a ferramenta não aplica sozinha.


Por fim, essas observações conversam de perto com o parecer recebido na Entrega 01, que apontou falta de rastro para as fontes e para os artefatos correlacionados, além da ausência de registro da dinâmica da equipe. Trabalhar com IA Generativa tende a agravar justamente esses dois pontos: é fácil produzir texto convincente sem fonte declarada, e a elaboração migra para conversas individuais que não deixam vestígio para o grupo. As práticas combinadas na reunião respondem a isso — exigir arquivo e linha para toda referência ao sistema analisado, citar as fontes no corpo do texto e não apenas na lista final, registrar as discussões de revisão na página de atas e indicar como revisor alguém da própria subequipe. No balanço da entrega, a IA Generativa acelerou bastante a construção dos artefatos, mas transferiu esforço para a verificação dos fatos e para a integração entre os modelos, que passaram a exigir bem mais atenção do que exigiriam sem ela.

## Evidências de Participação

| Integrante | Atividade/Contribuição | Evidência |
|:---|:---|:---|
| [Caio Alexandre](https://github.com/bitterteriyaki) | Elaboração do Diagrama de Componentes (FOCO_01), do Diagrama de Casos de Uso e do Diagrama de Sequência (FOCO_02), e das iniciativas extras de suporte a PlantUML e padronização do ambiente local. | [FOCO 01](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/commit/98371918639c591737a2dec2d54202a70601cf9b) · [FOCO 02](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/commit/be59a0f70e3df63d63b5dba50b58155ababd0119) · [PlantUML](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/commit/2f57d45a1a127f3498532aa3f49f5fc774a21f15) · [mise](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/commit/c9513c3da47eef8688133a4c7b16b0fbbb8418e9) · [Iniciativas Extras](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/commit/5fe61269c7e08667d88afc95674c206936147b6a) |
| [Guilherme Moura](https://github.com/Guilherme-Moura) | Elaboração do Diagrama de Classes (FOCO_01) e do Diagrama de Comunicação (FOCO_02). | [Commit](LINK_DO_COMMIT) |
| [Leonardo Fachinello Bonetti](https://github.com/LeoFacB) | Estruturação do documento de Modelagem Estática, elaboração do Diagrama de Implantação (FOCO_01) e do Diagrama de Estados (FOCO_02), e elaboração da ata da reunião da subequipe. | [PR #7 — Modelagem Estática](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/pull/7) · [PR #15 — FOCO 01](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/pull/15) · [PR #16 — FOCO 02](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/pull/16) · [PR #22 — Ata da reunião](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/pull/22) |

<p align="center">Tabela 1: Evidências de participação dos integrantes.</p>

## Evidências do Uso de IA Generativa

| Integrante | Ferramenta | Finalidade | Evidência |
|:---|:---|:---|:---|
| Caio Alexandre Ornelas Silva | Claude (Claude Code) | Aceleração do desenvolvimento dos artefatos da entrega, com apoio na elaboração dos diagramas UML em PlantUML e da documentação associada, e automação do versionamento (organização dos commits, redação das mensagens e descrição do *pull request*). | [Histórico de commits](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/commits/main?author=bitterteriyaki) · [Commits da branch `docs/sub03-caio`](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/commits/docs/sub03-caio) |
| Guilherme Moura da Silva Neto | Gemini | Geração de código-base em PlantUML para os Diagramas de Classes e de Comunicação e apoio na estruturação, revisão e refinamento da documentação. | [Print da Versão Inicial](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/blob/main/docs/Base/images/SubEquipe_03/diagrama-versao-inicial-ia.png) |
| Leonardo Fachinello Bonetti | Claude (Claude Code) | Análise do repositório de referência com levantamento de arquivo e linha, elaboração do código PlantUML do Diagrama de Implantação e do Diagrama de Estados, organização dos commits e transcrição resumida da ata da reunião da subequipe. | [Registro](https://claude.ai/share/f668a995-9b24-4f28-8ee8-d1c0e86cf613) |

<p align="center">Tabela 2: Evidências do uso de IA Generativa.</p>

## Referências

ANTHROPIC. **Claude**. Disponível em: [https://www.anthropic.com/claude](https://www.anthropic.com/claude). Acesso em: 18 set. 2026.

ANTHROPIC. **Claude Code: documentação oficial**. Disponível em: [https://docs.claude.com/en/docs/claude-code](https://docs.claude.com/en/docs/claude-code). Acesso em: 18 set. 2026.

GOOGLE. **Gemini**. Disponível em: [https://gemini.google.com](https://gemini.google.com). Acesso em: 18 set. 2026.

## Nível de Contribuição dos Integrantes

| Nome | % de Contribuição |
|:---|:---:|
| [Caio Alexandre](https://github.com/bitterteriyaki) | 30% |
| [Guilherme Moura](https://github.com/Guilherme-Moura) | 30% |
| [Leonardo Fachinello Bonetti](https://github.com/LeoFacB) | |

<p align="center">Tabela 3: Contribuição dos integrantes.</p>

## Histórico de Versões

| Versão | Data | Descrição | Autor(es) | Revisor(es) | Detalhe da Revisão |
|:------:|:----:|:----------|:----------|:------------|:-------------------|
| 1.0 | 13/09/2026 | Criação do documento de IA Generativa da SubEquipe_03. | [Arthur Fernandes](https://github.com/arthurfernandesj) |  | Criação da estrutura inicial para registro das lições aprendidas e do uso crítico de IA Generativa pelos integrantes. |
| 1.1 | 17/09/2026 | Reestruturação do documento e registro da experiência individual do integrante. | [Caio Alexandre](https://github.com/bitterteriyaki) | [Arthur Fernandes](https://github.com/arthurfernandesj) | Substituição da tabela de pontos de vista por seções individuais por integrante, inclusão das seções de Análise Crítica e de Evidências de Participação e de Uso de IA Generativa, e registro do ponto de vista do integrante Caio Alexandre. |
| 1.2 | 17/09/2026 | Registro do uso de IA Generativa na automação do versionamento. | [Caio Alexandre](https://github.com/bitterteriyaki) | [Arthur Fernandes](https://github.com/arthurfernandesj) | Inclusão, no ponto de vista individual e na tabela de evidências, do uso da ferramenta na organização dos commits, na redação das mensagens e na elaboração da descrição do pull request, com o histórico de commits como evidência. |
| 1.3 | 17/09/2026 | Registro do uso de IA Generativa e lições aprendidas do integrante Guilherme Moura. | [Guilherme Moura](https://github.com/Guilherme-Moura) | | Inclusão do relato individual sobre a geração de código-base em PlantUML para os diagramas (Classes e Comunicação), refinamento manual e suporte na formatação da documentação técnica, com respectiva atualização da tabela de evidências. |
| 1.4 | 17/09/2026 | Correção da lista de integrantes e atualização das contribuições. | [Guilherme Moura](https://github.com/Guilherme-Moura) | | Correção dos nomes dos membros da SubEquipe_03 e preenchimento da porcentagem de contribuição individual na tabela correspondente. |
| 1.5 | 17/09/2026 | Registro do ponto de vista do integrante Leonardo Bonetti e elaboração da análise crítica coletiva. | [Leonardo Fachinello Bonetti](https://github.com/LeoFacB) |  | Inclusão das lições aprendidas e do relato de uso da ferramenta pelo integrante, abrangendo a análise do repositório de referência, a elaboração do código PlantUML do Diagrama de Implantação e do Diagrama de Estados e a redação da documentação associada. Elaboração da seção de Análise Crítica, reunindo as experiências dos três integrantes e as deliberações da reunião da subequipe, com registro das divergências de nomenclatura entre os artefatos, da tendência à consistência aparente e da relação entre o uso da ferramenta e o parecer recebido na Entrega 01. Atualização das tabelas de evidências de participação e de uso de IA Generativa. |

<p align="center">Tabela 4: Histórico de Versões.</p>

Ver também: [Modelagem Estática na Notação UML](ModelagemEstatica.md) · [Modelagem Dinâmica na Notação UML](ModelagemDinamica.md)
