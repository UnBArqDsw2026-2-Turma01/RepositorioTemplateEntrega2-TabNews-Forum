# SubEquipe_01 — Modelagem Estática na Notação UML

## Descrição

Modelagem estática da SubEquipe_01, no escopo do **FOCO_01 — Modelagem Estática na Notação UML**. O documento apresenta a modelagem estrutural do sistema Fórum, utilizando a notação UML para representar suas principais classes, atributos, métodos e relacionamentos, bem como a organização do sistema em componentes de software.

A modelagem tem como objetivo representar a estrutura do software de forma clara, permitindo visualizar os principais elementos que compõem o sistema e suas relações.

## Objetivo

Elaborar uma modelagem estática em UML para o sistema Fórum, evidenciando suas principais classes, responsabilidades, atributos, métodos e relacionamentos, além da organização em componentes e interfaces, de forma a facilitar a compreensão da estrutura do software e apoiar sua implementação, manutenção e evolução.

## Metodologia

A modelagem estática foi elaborada a partir da análise do escopo do produto, das funcionalidades previstas para o sistema e dos artefatos desenvolvidos anteriormente pela equipe.

O processo envolveu a identificação das principais entidades e responsabilidades do sistema, buscando determinar quais elementos deveriam ser representados como classes, seus respectivos atributos e métodos, além dos relacionamentos existentes entre elas.

Para a elaboração do modelo, foram consideradas as principais funcionalidades do Fórum, incluindo cadastro e autenticação de usuários, criação e visualização de publicações, respostas, organização por categorias, avaliações, interações e busca de discussões.

Como complemento à visão orientada a classes, foi elaborado também um **Diagrama de Componentes** para a funcionalidade de Login e Autenticação, elevando o nível de abstração para representar como o sistema se organiza em componentes de software e quais interfaces esses componentes fornecem e requerem. Essa etapa foi apoiada pela engenharia reversa do fluxo de login do TabNews e pela documentação pública do projeto, que é de código aberto.

A modelagem foi desenvolvida de forma colaborativa pelos integrantes da SubEquipe_01, utilizando a notação UML para representar os elementos estruturais identificados.

As decisões de modelagem buscaram manter um nível de abstração adequado ao objetivo da entrega, priorizando os elementos diretamente relacionados ao funcionamento do sistema e evitando detalhamentos de implementação que não fossem necessários para a representação estática.

## Escolha da Modelagem

Para o **FOCO_01 — Modelagem Estática na Notação UML**, a SubEquipe_01 adotou o **Diagrama de Classes** como modelo principal e o **Diagrama de Componentes** como modelo complementar.

A escolha do Diagrama de Classes foi realizada por esse modelo permitir representar de forma direta a estrutura do sistema, evidenciando as classes, seus atributos, métodos e os relacionamentos existentes entre os elementos.

O Diagrama de Classes também permite estabelecer uma visão estrutural do domínio do Fórum, relacionando funcionalidades previstas no escopo do produto aos elementos que compõem a solução.

Além do modelo geral do sistema, foi elaborado um recorte específico relacionado ao **Login e Autenticação**, permitindo detalhar uma parte da modelagem e evidenciar a contribuição individual realizada nessa funcionalidade.

Por fim, para essa mesma funcionalidade de Login e Autenticação, foi elaborado um **Diagrama de Componentes**. Enquanto o Diagrama de Classes descreve a estrutura interna do domínio (classes, atributos e relacionamentos), o Diagrama de Componentes descreve a organização do sistema em unidades de software implantáveis e as interfaces trocadas entre elas. Ambos são modelos estáticos (estruturais), pois representam a organização do sistema em tempo de projeto, e não a ordem temporal de execução — que é objeto da modelagem dinâmica.

## Modelagem Estática

### Diagrama de Classes

O Diagrama de Classes apresenta uma visão geral da estrutura do sistema Fórum, representando os principais elementos necessários para o funcionamento das funcionalidades previstas no escopo do produto.

Entre os elementos representados estão as classes relacionadas aos usuários, autenticação, sessões, publicações, comentários, categorias, avaliações, interações e busca.

A organização das classes busca demonstrar as responsabilidades de cada elemento e os relacionamentos existentes entre eles, proporcionando uma visão estrutural do sistema.

<div align="center">
<img src="Base/images/diagrama_completo.png" alt="Diagrama de Classes completo do sistema Fórum" width="800">
</div>

<p align="center">Figura 1: Diagrama de Classes completo do sistema Fórum. Fonte: SubEquipe_01 (2026).</p>

### Recorte — Login e Autenticação

Como detalhamento da modelagem, foi elaborado um recorte do Diagrama de Classes relacionado ao processo de **Login e Autenticação**.

O recorte representa as principais classes envolvidas nesse processo: `Usuario`, `Credencial`, `Autenticacao` e `Sessao`.

A classe `Usuario` representa o usuário do sistema e mantém sua relação com as credenciais utilizadas no processo de autenticação. A classe `Credencial` concentra as informações necessárias para validação das credenciais de acesso.

A classe `Autenticacao` representa o processo de validação e autenticação do usuário, enquanto a classe `Sessao` representa a sessão criada após a autenticação, incluindo informações relacionadas ao seu controle e validade.

<div align="center">
<img src="Base/images/diagrama_login.png" alt="Recorte do Diagrama de Classes de Login e Autenticação" width="800">
</div>

<p align="center">Figura 2: Recorte do Diagrama de Classes — Login e Autenticação. Fonte: SubEquipe_01 (2026).</p>

### Diagrama de Componentes — Login e Autenticação

Complementando a visão orientada a classes, foi elaborado um **Diagrama de Componentes** para a funcionalidade de Login e Autenticação. O objetivo desse modelo é representar como o sistema se organiza em componentes de software e como esses componentes se comunicam por meio de **interfaces fornecidas e requeridas** (notação *ball-and-socket*).

O diagrama organiza a solução em três camadas:

- **Cliente (Navegador):** a **UI de Autenticação** (Next.js/React), que agrupa os formulários de login, cadastro e recuperação de senha responsáveis por capturar os dados do usuário.
- **Servidor de Aplicação (API TabNews):** a **API de Sessões** (`/api/v1/sessions`), que atua como ponto de entrada da autenticação e orquestra os componentes de **Rate Limiter** (proteção da rota de login), **Serviço de Autenticação**, **Serviço de Usuários**, **Gerenciador de Sessão (Token)** e **Serviço de Recuperação de Senha**.
- **Serviços de Infraestrutura:** o **Banco de Dados (PostgreSQL)**, que persiste usuários, credenciais e sessões; o **Serviço de E-mail**, responsável pelo envio do link de recuperação; e o **Cache / Rate Limit (Upstash Redis)**, que armazena os contadores de requisições utilizados pelo Rate Limiter.

<div align="center">
<img src="Base/images/diagrama_componentes.png" alt="Diagrama de Componentes da funcionalidade de Login e Autenticação" width="800">
</div>

<p align="center">Figura 3: Diagrama de Componentes — Login e Autenticação. Fonte: SubEquipe_01 (2026).</p>

O quadro a seguir resume as interfaces representadas no diagrama, com seus componentes fornecedores e consumidores:

| Interface | Fornecida por | Requerida por |
|:---|:---|:---|
| `IAutenticacao` | API de Sessões | Formulário de Login / Cadastro |
| `IRecuperacaoSenha` | Serviço de Recuperação de Senha | Formulário de Recuperação de Senha |
| `IControleRequisicoes` | Rate Limiter | API de Sessões |
| `IValidacaoCredencial` | Serviço de Autenticação | API de Sessões |
| `IGerenciarSessao` | Gerenciador de Sessão | API de Sessões |
| `IConsultaUsuario` | Serviço de Usuários | Serviço de Autenticação / Serviço de Recuperação de Senha |
| `IEnvioEmail` | Serviço de E-mail | Serviço de Recuperação de Senha |
| `IPersistencia` | Banco de Dados (PostgreSQL) | Serviço de Usuários / Gerenciador de Sessão |

<p align="center">Tabela 1: Interfaces do Diagrama de Componentes de Login e Autenticação.</p>

O Diagrama de Componentes mantém **rastreabilidade** com o recorte do Diagrama de Classes: as classes `Usuario` e `Credencial` são manipuladas pelos componentes **Serviço de Usuários** e persistidas pelo **Banco de Dados**; a classe `Autenticacao` corresponde ao comportamento encapsulado no **Serviço de Autenticação**; e a classe `Sessao` corresponde ao **Gerenciador de Sessão (Token)**. Dessa forma, os dois modelos descrevem a mesma funcionalidade sob perspectivas complementares — o de classes no nível do domínio e o de componentes no nível arquitetural.

## Senso Crítico e Decisões de Modelagem

Durante a elaboração do modelo, a SubEquipe_01 avaliou quais elementos deveriam ser representados no Diagrama de Classes, considerando o escopo definido para o sistema e o nível de abstração adequado para a entrega.

Foi priorizada a representação das classes e relacionamentos diretamente relacionados às principais funcionalidades do Fórum, evitando a inclusão de elementos excessivamente específicos de implementação.

No recorte de Login e Autenticação, foram destacadas as classes `Usuario`, `Credencial`, `Autenticacao` e `Sessao`, por representarem os principais elementos envolvidos no processo de acesso ao sistema.

A definição dos relacionamentos buscou representar as responsabilidades e dependências entre os elementos de forma coerente com o funcionamento esperado da aplicação.

Durante a construção do modelo, também foi avaliada a necessidade de manter uma representação suficientemente abrangente para contemplar as principais funcionalidades do Fórum, sem tornar o diagrama excessivamente complexo ou específico de implementação.

Na elaboração do Diagrama de Componentes, a SubEquipe_01 optou por representar a funcionalidade de Login e Autenticação em um nível arquitetural, priorizando os componentes e interfaces essenciais ao fluxo de autenticação. Decidiu-se explicitar componentes de infraestrutura relevantes ao comportamento observado do sistema — como o Rate Limiter e o cache de contadores — por serem elementos que impactam diretamente a segurança e o funcionamento do login, evitando, ainda assim, detalhamentos internos de implementação que não agregassem à visão estrutural.

## Decisões e Consensos da SubEquipe

Durante a elaboração da modelagem estática, foram discutidas as principais entidades do sistema e a forma mais adequada de representar suas responsabilidades e relacionamentos.

Como decisão da SubEquipe_01, foi adotado o **Diagrama de Classes** como representação principal da modelagem estática, por permitir apresentar de forma integrada os elementos estruturais do sistema Fórum.

Também foi definido que o modelo geral deveria contemplar as principais funcionalidades identificadas no escopo do produto, incluindo usuários, autenticação, publicações, comentários, categorias, avaliações, interações e busca.

Para o processo de Login e Autenticação, foi definido um recorte específico com as classes `Usuario`, `Credencial`, `Autenticacao` e `Sessao`, permitindo detalhar essa parte da estrutura do sistema.

Foi definido, ainda, que essa mesma funcionalidade seria representada por um **Diagrama de Componentes**, de modo a oferecer uma visão arquitetural complementar ao recorte de classes e evidenciar a organização do sistema em componentes e interfaces.

As decisões apresentadas nesta seção foram consolidadas na versão utilizada pela SubEquipe_01 para a entrega.

## Pontos de Vista dos Integrantes

### Arthur Fernandes

A elaboração do Diagrama de Classes permitiu compreender melhor como as funcionalidades do Fórum podem ser representadas estruturalmente por meio de classes e relacionamentos.

A construção do modelo também evidenciou a importância de definir responsabilidades para cada classe antes de estabelecer seus relacionamentos, evitando representar funcionalidades diretamente como elementos isolados do sistema.

### Giovana Fontes

A modelagem do processo de Login e Autenticação permitiu compreender a separação das responsabilidades entre usuário, credenciais, autenticação e sessão.

O recorte também contribuiu para visualizar como o processo de autenticação pode ser representado estruturalmente, facilitando a compreensão das relações entre os elementos envolvidos.

### [preencher — autor(a) do Diagrama de Componentes]

A elaboração do Diagrama de Componentes permitiu enxergar a funcionalidade de Login e Autenticação sob uma perspectiva arquitetural, evidenciando como os componentes se comunicam por meio de interfaces fornecidas e requeridas.

A construção do modelo também reforçou a importância de distinguir a visão de domínio (classes) da visão de organização do software (componentes), e de manter a rastreabilidade entre elas, garantindo que ambos os diagramas representem de forma coerente a mesma funcionalidade.

## Participação e Evidências

A participação dos integrantes da SubEquipe_01 foi distribuída de acordo com as atividades realizadas durante a elaboração da modelagem estática.

| Integrante | Contribuição | Evidência |
|:---|:---|:---|
| [Arthur Fernandes](https://github.com/arthurfernandesj) | Estrutura geral do Diagrama de Classes, organização da documentação e ajustes da modelagem. | [Commit/PR](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/pull/2) |
| [Giovana Fontes](https://github.com/GiovanaFontesS) | Modelagem do recorte de Login e Autenticação. | [Commit/PR](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/pull/1) |
| [preencher](https://github.com/preencher) | Elaboração do Diagrama de Componentes da funcionalidade de Login e Autenticação. | [Commit/PR](https://github.com/UnBArqDsw2026-2-Turma01/RepositorioTemplateEntrega2-TabNews-Forum/pull/preencher) |

As evidências apresentadas devem permitir a identificação da participação individual de cada integrante por meio do histórico de versões, commits ou Pull Requests do repositório.

## Nível de Contribuição dos Integrantes

| Nome | % de Contribuição |
|:---|:---:|
| [Arthur Fernandes](https://github.com/arthurfernandesj) | |
| [Giovana Fontes](https://github.com/GiovanaFontesS) | |
| [preencher](https://github.com/preencher) | |


<p align="center">Tabela 2: Contribuição dos integrantes.</p>

---

## Referências

LUCID SOFTWARE INC. **Tutorial de diagrama de classes UML**. Disponível em: [https://app.lucid.co/pt/diagrama/uml/tutorial-de-diagrama-de-classes](https://app.lucid.co/pt/diagrama/uml/tutorial-de-diagrama-de-classes). Acesso em: 15 set. 2026.

LUCID SOFTWARE INC. **Tutorial de diagrama de componentes UML**. Disponível em: [https://www.lucidchart.com/pages/pt/diagrama-de-componentes-uml](https://www.lucidchart.com/pages/pt/diagrama-de-componentes-uml). Acesso em: 17 set. 2026.

OBJECT MANAGEMENT GROUP. **OMG Unified Modeling Language (OMG UML), Version 2.5.1**. 2017. Disponível em: [https://www.omg.org/spec/UML/2.5.1/PDF](https://www.omg.org/spec/UML/2.5.1/PDF). Acesso em: 15 set. 2026.

TABNEWS. **Repositório oficial (código aberto)**. Disponível em: [https://github.com/filipedeschamps/tabnews.com.br](https://github.com/filipedeschamps/tabnews.com.br). Acesso em: 17 set. 2026.

UNB FCTE — ARQDSW. **Módulo de Modelagem**. Disponível em: [https://sites.google.com/view/unb-fcte-arqdsw/módulos/módulo-modelagem?authuser=0](https://sites.google.com/view/unb-fcte-arqdsw/módulos/módulo-modelagem?authuser=0). Acesso em: 15 set. 2026.

---

## Histórico de Versões

| Versão | Data | Descrição | Autor(es) | Revisor(es) | Detalhe da Revisão |
|:------:|:----:|:----------|:----------|:------------|:-------------------|
| 1.0 | 13/09/2026 | Criação do documento de Modelagem Estática na Notação UML da SubEquipe_01. | [Arthur Fernandes](https://github.com/arthurfernandesj) | [Giovana Fontes](https://github.com/GiovanaFontesS) | Criação da estrutura inicial do documento, definição do escopo da modelagem estática e organização das primeiras seções da documentação. |
| 1.1 | 15/09/2026 | Elaboração do Diagrama de Classes completo do sistema Fórum. | [Arthur Fernandes](https://github.com/arthurfernandesj) | [Giovana Fontes](https://github.com/GiovanaFontesS) | Desenvolvimento do modelo estrutural completo do sistema, contemplando as classes Usuario, Credencial, Autenticacao, Sessao, RecuperacaoSenha, Perfil, Publicacao, Comentario, Categoria, Avaliacao, Interaçao e Busca, além da definição de seus atributos, métodos, relacionamentos e multiplicidades. |
| 1.2 | 16/09/2026 | Elaboração da modelagem relacionada ao Login e Autenticação. | [Giovana Fontes](https://github.com/GiovanaFontesS) | [Arthur Fernandes](https://github.com/arthurfernandesj) | Desenvolvimento do recorte do Diagrama de Classes referente ao Login e Autenticação, contemplando as classes Usuario, Credencial, Autenticacao e Sessao, seus atributos, métodos e principais relacionamentos. |
| 1.3 | 17/09/2026 | Ajustes e atualização do documento de Modelagem Estática. | [Arthur Fernandes](https://github.com/arthurfernandesj) | [Giovana Fontes](https://github.com/GiovanaFontesS) | Revisão e integração das contribuições da SubEquipe_01, ajustes na estrutura e descrição do documento, organização do Diagrama de Classes completo, adequação do recorte de Login e Autenticação, correção dos caminhos das imagens e atualização da documentação para a entrega. |
| 1.4 | 17/09/2026 | Adição do Diagrama de Componentes da funcionalidade de Login e Autenticação. | [preencher](https://github.com/preencher) | [preencher](https://github.com/preencher) | Elaboração do Diagrama de Componentes referente ao Login e Autenticação, incluindo os componentes de UI, API de Sessões, Rate Limiter, Serviço de Autenticação, Serviço de Usuários, Gerenciador de Sessão, Serviço de Recuperação de Senha, Banco de Dados, Serviço de E-mail e Cache/Rate Limit, com suas respectivas interfaces fornecidas e requeridas. Atualização das seções de metodologia, escolha da modelagem, senso crítico, decisões da subequipe, pontos de vista, participação e referências para contemplar o novo diagrama. |

<p align="center">Tabela 3: Histórico de Versões.</p>

---

Ver também: [Modelagem Dinâmica na Notação UML](ModelagemDinamica.md) · [IA Generativa](IAGenerativa.md)
