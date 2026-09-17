# SubEquipe_02 — Modelagem Dinâmica na Notação UML

## Descrição

Modelagem do processo de negócio da SubEquipe_02, no escopo do **FOCO_02 — Modelagem Dinâmica na Notação UML**. O documento apresenta a modelagem dinâmica do software utilizando a notação UML, buscando representar o comportamento do sistema e a interação entre seus principais elementos ao longo da execução dos processos.

## Objetivo

Elaborar uma modelagem dinâmica em UML para o sistema desenvolvido pela equipe, evidenciando o comportamento dos processos, as atividades realizadas, os eventos, as interações e os pontos de decisão envolvidos na execução das funcionalidades do sistema.

## Metodologia

A modelagem dinâmica foi elaborada a partir da análise dos processos e das funcionalidades do sistema, buscando representar o comportamento da aplicação e a sequência de eventos envolvidos em sua execução.

O processo envolveu a identificação dos principais fluxos e interações do sistema, considerando as ações realizadas pelos usuários e as respostas produzidas pela aplicação. A partir dessa análise, foram definidos os elementos necessários para representar o comportamento do processo utilizando a notação UML.

A elaboração do modelo foi realizada de forma colaborativa pelos integrantes da SubEquipe_02, utilizando as ferramentas adotadas pela equipe para construção e documentação dos diagramas.

As decisões de modelagem foram fundamentadas nos conceitos da UML e na literatura de Engenharia de Software, buscando representar de maneira clara e consistente o comportamento do sistema.

## Conteúdo

### Modelagem Dinâmica

A **modelagem dinâmica** representa o comportamento de um sistema durante sua execução, mostrando como seus componentes, objetos ou usuários **interagem ao longo do tempo**. Diferentemente da modelagem estática, que descreve a estrutura do sistema e seus elementos, a modelagem dinâmica busca representar **fluxos, eventos, mensagens e mudanças de estado**.

### Diagrama de Sequência do TabNews — Isaac Menezes

O modelo foi construído usando o site plantuml.com e sua linguagem descritiva padrão. 
Todos os casos de uso, gates, lifetimes, visões e psicinas foram pensadas a partir dos seguintes objetos presentes no fórum:
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

De maneira evidente, esses objetos foram melhor ajustados, levando em consideração seus comportamentos e dependências no site, para gerar o seguinte Diagrama de Sequência.

<div align="center">
  <img src="Base/images/modeloSequencia1_isaacMenezes.png" alt="Diagrama Sequencial" width="800">
  
  <p><strong>Figura 1:</strong> Diagrama Sequencial. Fonte: SubEquipe_02 (2026).</p>
</div>

O Diagrama mostra as relações dinâmicas que o usuário tem com diversos componentes do fórum, detre eles, API, publicações, banco de dados, etc. As respectivas piscinas de cada interação também estão representadas.
O Diagrama foi feito na linguagem descritiva padrão do plantuml.com e o link para o script é este: https://drive.google.com/file/d/1Uyj1VkuLbT1S0bWx4iKhvRRACIL9Z8ka/view?usp=sharing

## Referências

H. Washizaki, eds., Guide to the Software Engineering Body of Knowledge (SWEBOK Guide), Version 4.0, IEEE Computer Society, 2024. Acesso em 14 set. de 2026.

## Nível de Contribuição dos Integrantes

| Nome | % de Contribuição |
|------|-------------------|
| Isaac Menezes| 33% |
|      |                   |
|      |                   |

<p align="center">Tabela 1: Contribuição dos integrantes.</p>

## Histórico de Versões

| Versão | Data | Descrição | Autor(es) | Revisor(es) | Detalhe da Revisão |
|:------:|:----:|:----------|:----------|:------------|:-------------------|
| 1.0 | 13/09/2026 | Criação do documento de Modelagem Dinâmica na Notação UML da SubEquipe_02. |   |  | Criação da estrutura inicial do documento e preparação para inserção da modelagem dinâmica. |
| 1.1 | 16/09/2026 | Teste inicial de permissão de contribuição. |[Isaac Menezes Pereira](https://github.com/pratamz250) |  | Apenas inserido nome. |
| 1.2 | 17/09/2026 | Inserção de Diagrama de Sequência |[Isaac Menezes Pereira](https://github.com/pratamz250) |  | Diagrama de Sequência inserido, construído no plantuml.com com sua linguagem descritiva padrão. |

<p align="center">Tabela 2: Histórico de Versões.</p>

Ver também: [Modelagem Estática na Notação UML](ModelagemEstatica.md) · [IA Generativa](IAGenerativa.md)