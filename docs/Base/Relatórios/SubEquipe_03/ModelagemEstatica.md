# SubEquipe_03 — Modelagem Estática na Notação UML

## Descrição

Modelagem estática da funcionalidade **Página da postagem** do TabNews, no escopo do **FOCO_01 — Modelagem Estática na Notação UML**. O documento representa a estrutura da publicação expandida, incluindo seu conteúdo, a árvore de comentários e a votação em TabCoins, utilizando três tipos diferentes de diagramas estáticos para oferecer visões arquiteturais complementares.

## Objetivo

Representar as principais classes, atributos, métodos e relacionamentos envolvidos na Página da postagem, mantendo o nível de abstração adequado à funcionalidade analisada.

## Metodologia

A modelagem foi elaborada a partir da análise detalhada da funcionalidade Página da postagem no sistema TabNews. Em vez de utilizar recortes detalhados de um único diagrama, a equipe optou por desenvolver três tipos distintos de diagramas. Todos os três têm como escopo a página completa, buscando uma visão abrangente da sua organização estrutural sob diferentes níveis de abstração.

## Escolha da Modelagem

A estratégia de modelagem adotada utilizou três diagramas UML distintos para representar o sistema sob diferentes perspectivas estruturais. Essa escolha visa mapear a página completa, aplicando múltiplos modelos estáticos que se complementam:
1. **Diagrama de Classes:** Focado na estrutura lógica e relacional dos dados (publicação, comentários, votos).
2. **Diagrama de Componentes:** Focado na organização modular, detalhando os artefatos de software que compõem a página e suas interfaces.
3. **[Terceiro Tipo a Definir]:** 

## Modelagem Estática

### 1. Diagrama de Classes

O Diagrama de Classes representa a estrutura lógica e de domínio de toda a Página da postagem, detalhando os atributos, métodos e os relacionamentos hierárquicos necessários para exibir a publicação e sua árvore de comentários.


<div align="center">
<img src="Base/images/SubEquipe_03/diagrama-classes.png" alt="Diagrama de Classes completo da Página da postagem" width="800">
</div>

<p align="center">Figura 1: Diagrama de Classes completo da Página da postagem. Fonte: SubEquipe_03 (2026).</p>

### 2. Diagrama de Componentes

Este diagrama oferece uma visão física e de subsistemas da Página da postagem completa, ilustrando como as partes modulares da aplicação se organizam e se conectam para fornecer a funcionalidade aos usuários.

<!-- ESPAÇO RESERVADO PARA O DIAGRAMA DE COMPONENTES
     Imagem:       Base/images/SubEquipe_03/diagrama-componentes.png
     Arquivo-fonte: Base/images/SubEquipe_03/fontes/diagrama-componentes.drawio
     Ao inserir, substituir este comentário por:

<div align="center">
<img src="Base/images/SubEquipe_03/diagrama-componentes.png" alt="Diagrama de Componentes da Página da postagem" width="800">
</div>

<p align="center">Figura 2: Diagrama de Componentes da Página da postagem. Fonte: SubEquipe_03 (2026).</p>
-->

### 3. [Nome do Terceiro Diagrama]

[Breve descrição estrutural do terceiro diagrama, explicando qual aspecto estático da página completa ele resolve, a ser preenchida após a definição da equipe.]

<!-- ESPAÇO RESERVADO PARA O TERCEIRO DIAGRAMA
     Imagem:       Base/images/SubEquipe_03/diagrama-3.png
     Arquivo-fonte: Base/images/SubEquipe_03/fontes/diagrama-3.drawio
     Ao inserir, substituir este comentário por:

<div align="center">
<img src="Base/images/SubEquipe_03/diagrama-3.png" alt="Diagrama 3 da Página da postagem" width="800">
</div>

<p align="center">Figura 3: Diagrama [Tipo] da Página da postagem. Fonte: SubEquipe_03 (2026).</p>
-->

## Referências

OBJECT MANAGEMENT GROUP. **OMG Unified Modeling Language (OMG UML), Version 2.5.1**. 2017. Disponível em: [https://www.omg.org/spec/UML/2.5.1/PDF](https://www.omg.org/spec/UML/2.5.1/PDF). Acesso em: 16 set. 2026.

UML-DIAGRAMS.ORG. **UML Class Diagrams**. Disponível em: [https://www.uml-diagrams.org/class-diagrams/class-diagram.html](https://www.uml-diagrams.org/class-diagrams/class-diagram.html). Acesso em: 16 set. 2026.


## Nível de Contribuição dos Integrantes

| Nome | % de Contribuição |
|------|-------------------|
|      |                   |
|      |                   |
|      |                   |

<p align="center">Tabela 1: Contribuição dos integrantes.</p>

## Histórico de Versões

| Versão | Data | Descrição | Autor(es) | Revisor(es) | Detalhe da Revisão |
|:------:|:----:|:----------|:----------|:------------|:-------------------|
| 1.0 | 13/09/2026 | Criação do documento de Modelagem Estática na Notação UML da SubEquipe_03. | [Arthur Fernandes](https://github.com/arthurfernandesj) |  | Criação da estrutura inicial do documento e preparação para inserção da modelagem estática. |
| 1.1 | 17/09/2026 | Estruturação do documento de Modelagem Estática para a funcionalidade Página da postagem. | [Leonardo Fachinello Bonetti](https://github.com/LeoFacB) | [Guilherme Moura](https://github.com/Guilherme-Moura) | Definição do escopo na Página da postagem, da metodologia e da justificativa do Diagrama de Classes, e organização das seções do Diagrama de Classes completo, do recorte da Árvore de Comentários e do recorte de Votação / TabCoins. |
| 1.2 | 17/09/2026 | Alteração da estrutura do documento e adição do Diagrama de Classes. | [Guilherme Moura](https://github.com/Guilherme-Moura) | | Atualização das seções de Metodologia e Escolha da Modelagem para refletir o uso de três modelos estáticos complementares, além da inserção do artefato visual do Diagrama de Classes. |

<p align="center">Tabela 2: Histórico de Versões.</p>

Ver também: [Modelagem Dinâmica na Notação UML](ModelagemDinamica.md) · [IA Generativa](IAGenerativa.md)