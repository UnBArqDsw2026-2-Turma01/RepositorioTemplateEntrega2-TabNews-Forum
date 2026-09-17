# SubEquipe_02 — Modelagem Estática na Notação UML

## Descrição

Modelagem do processo de negócio da SubEquipe_02, no escopo do **FOCO_01 — Modelagem Estática na Notação UML**. O documento apresenta a modelagem estática do software desenvolvido pela equipe, utilizando a notação UML para representar seus principais elementos estruturais e relacionamentos.

## Objetivo

Elaborar uma modelagem estática em UML para o sistema desenvolvido pela equipe, evidenciando seus principais elementos estruturais, relacionamentos e organização, de forma a facilitar a compreensão da estrutura do software.

## Metodologia

A modelagem estática foi elaborada a partir da análise do sistema e de suas principais funcionalidades, buscando identificar os elementos estruturais necessários para representar a solução.

O processo envolveu a identificação das principais entidades, classes, atributos, métodos e relacionamentos presentes no sistema, seguida da representação desses elementos utilizando a notação UML.

Para a elaboração do modelo, foram analisados os requisitos e as funcionalidades definidas para o projeto, relacionando-os aos elementos estruturais do software. A modelagem foi desenvolvida de forma colaborativa pelos integrantes da SubEquipe_02, utilizando as ferramentas adotadas pela equipe para elaboração e documentação dos modelos.

As decisões de modelagem foram fundamentadas nos conceitos da UML e na literatura de Engenharia de Software, buscando representar de maneira clara e consistente a estrutura do sistema.

## Conteúdo

### Modelagem Estática

### Diagrama de Pacotes do TabNews — Isaac Menezes

O modelo foi construído usando o site plantuml.com e sua linguagem descritiva padrão. 
Todos os componentes foram pensadas a partir dos seguintes objetos presentes no fórum:
- Aba Relevantes;
- Aba Recentes;
- Campo de pesquisa;
- Ícone de mudança de tema de cor;
- Função de login;
- Função de cadastro;
- Aba de publicações;
- Aba de comentários;
- Aba de classificados;
- Aba Todos;
- Lista de comentários;
- Botão para próxima página;
- Botão para página anterior;
- Botão de contato;
- Botão de FAQ;
- Botão com link do GitHub;
- Botões de FAQ, GitHub, Museu, RSS, Sobre, Termos de Uso e curso.dev.

De maneira evidente, esses objetos foram melhor ajustados, levando em consideração seus comportamentos e dependências no site, para gerar o seguinte Diagrama de Pacotes.

<div align="center">
  <img src="/docs/Base/images/modeloPacotes1_isaacMenezes.png" alt="Diagrama de pacotes" width="800">
  
  <p><strong>Figura 1:</strong> Diagrama de Pacotes. Fonte: SubEquipe_02 (2026).</p>
</div>

O Diagrama mostra as relações dinâmicas que o usuário tem com diversos pacotes do fórum, detre eles, Frontend, Backend, Pesquisa, Banco de dados, etc.
O Diagrama foi feito na linguagem descritiva padrão do plantuml.com e o link para o script é este: https://drive.google.com/file/d/1vNdjDWz9vci6-VCckC8cAPcvgJLjPlSB/view?usp=sharing

## Referências

H. Washizaki, eds., Guide to the Software Engineering Body of Knowledge (SWEBOK Guide), Version 4.0, IEEE Computer Society, 2024. Acesso em 14 set. de 2026.

## Nível de Contribuição dos Integrantes

| Nome | % de Contribuição |
|------|-------------------|
|Isaac Menezes|25%|
|      |                   |

<p align="center">Tabela 1: Contribuição dos integrantes.</p>

## Histórico de Versões

| Versão | Data | Descrição | Autor(es) | Revisor(es) | Detalhe da Revisão |
|:------:|:----:|:----------|:----------|:------------|:-------------------|
| 1.0 | 13/09/2026  | Criação do documento de Modelagem Estática na Notação UML da SubEquipe_02. | [Arthur Fernandes](https://github.com/arthurfernandesj) |  | Criação da estrutura inicial do documento e preparação para inserção da modelagem estática. |
| 1.1 | 17/09/2026  | Inserção de Diagrama de Pacotes. | [Isaac Menezes](https://github.com/pratamz250) |  | Inserção de Diagrama de Pacotes. |

<p align="center">Tabela 2: Histórico de Versões.</p>

Ver também: [Modelagem Dinâmica na Notação UML](ModelagemDinamica.md) · [IA Generativa](IAGenerativa.md)