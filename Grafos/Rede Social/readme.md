# 📊 Projeto ConectaUDF — Redes Sociais com Grafos

## 📌 Sobre o projeto

Este projeto foi desenvolvido como atividade prática da disciplina de **Estrutura de Dados**, com o objetivo de estudar e aplicar os conceitos de Teoria dos Grafos utilizando Python.

A atividade consiste em representar uma rede social fictícia chamada **ConectaUDF**, na qual os usuários são representados por vértices e suas amizades por arestas.

A partir dessa representação, foram realizados cálculos e análises para compreender a estrutura da rede social, identificar usuários com maior número de conexões e explorar possibilidades de recomendação de novas amizades.

O trabalho foi desenvolvido em grupo, em parceria entre **Amanda Nogueira** e **Silviane Souza**.

## 🎯 Objetivos

- Compreender os conceitos fundamentais da Teoria dos Grafos.
- Representar uma rede social por meio de um grafo não direcionado.
- Utilizar listas de adjacência para armazenar as conexões entre os usuários.
- Calcular o grau dos vértices.
- Determinar a quantidade de arestas e a densidade do grafo.
- Identificar caminhos entre diferentes usuários.
- Implementar os cálculos utilizando Python.
- Ampliar a rede social e comparar os resultados antes e depois da expansão.

## 🧠 Conceitos aplicados

Durante o desenvolvimento da atividade, foram trabalhados os seguintes conceitos:

| Conceito | Descrição |
|---|---|
| Vértice (nó) | Representa um usuário da rede social. |
| Aresta | Representa uma amizade entre dois usuários. |
| Grau | Quantidade de conexões diretas de um usuário. |
| Caminho | Sequência de vértices conectados por arestas. |
| Grafo não direcionado | Representa relações recíprocas entre os usuários. |
| Lista de adjacência | Estrutura utilizada para armazenar os vértices e suas conexões. |
| Densidade | Proporção entre as conexões existentes e as conexões possíveis. |

## 🛠️ Tecnologias utilizadas

- **Python 3**
- **Google Colab**
- **GitHub**
- **Markdown**

## 📂 Estrutura da pasta

```text
grafo/
│
├── readme.md
│
├── Algoritmo_Grafos.ipyng
│
└── Atividade_Caderno do Estudante - grafos.pdf
```

## 📈 Desenvolvimento da atividade

### 1. Construção do grafo original

Inicialmente, foi criada uma rede social com seis usuários:

- Ana
- Bruno
- Carla
- Diego
- Elisa
- Felipe

As amizades foram representadas por um grafo não direcionado, considerando que toda amizade é recíproca.

### 2. Cálculo dos graus

Foi realizada a identificação da quantidade de conexões diretas de cada usuário.

Na rede original, os usuários Bruno, Carla, Diego e Elisa apresentaram o maior grau, com três conexões cada.

### 3. Cálculo das arestas e da densidade

A quantidade de arestas foi determinada por meio da soma dos graus dividida por dois, evitando contar cada amizade duas vezes.

A densidade foi calculada utilizando a fórmula:

\[
D = \frac{2E}{V(V-1)}
\]

Onde:
- D = densidade;
- E = quantidade de arestas;
- V = quantidade de vértices.

### 4. Identificação de caminhos

Foram identificados caminhos entre Ana e Felipe, demonstrando como diferentes usuários podem estar conectados mesmo sem possuírem uma amizade direta.

### 5. Ampliação da rede social

Na segunda parte da atividade, a rede foi ampliada com a inclusão de oito novos usuários fictícios:

- Gabriel
- Helena
- Irene
- João
- Laura
- Marta
- Amanda
- Silviane

Também foram adicionadas novas amizades, permitindo analisar o comportamento do grafo com uma quantidade maior de participantes.

## 📊 Resultados obtidos

Foi realizada uma comparação entre a rede social original e a rede ampliada.

| Indicador | Rede original | Rede ampliada |
|---|---:|---:|
| Usuários (vértices) | 6 | 14 |
| Amizades (arestas) | 8 | 25 |
| Amizades possíveis | 15 | 91 |
| Densidade | 53,33% | 27,47% |

A análise demonstrou que, mesmo com o aumento da quantidade de usuários e amizades, a densidade da rede diminuiu.

Isso ocorreu porque o número de conexões possíveis cresceu proporcionalmente mais do que o número de amizades efetivamente estabelecidas.

Na rede ampliada, **Gabriel** apresentou o maior grau, com cinco conexões diretas.

💻 Como executar

O código foi desenvolvido utilizando Python no Google Colab.

Para executar:

Acesse o Google Colab.

Faça o upload do arquivo Rede_Social.ipyng.

Abra o notebook.

Execute as células utilizando a opção Executar tudo ou execute cada célula individualmente.

Observe os resultados dos cálculos e das análises da rede social.

📄 Arquivos do projeto

Arquivo

Descrição

Rede_Social.ipyng

Notebook Python desenvolvido no Google Colab, contendo a implementação da rede social e os cálculos realizados.

Atividade_Resposta_Caderno do Estudante - grafos.pdf

Documento com as respostas, tabelas, cálculos e representações gráficas desenvolvidos durante a atividade.

👥 Integrantes

[Amanda de Souza Nogueira](https://github.com/Nogueira-Amanda/Estrutura_Dados_II/tree/main/Grafos/Atividade%20Rede%20Social)

Silviane Souza

📚 Considerações finais

O desenvolvimento deste projeto proporcionou a aplicação prática dos conceitos de Teoria dos Grafos e sua utilização na representação de redes sociais.

Por meio do Python e das listas de adjacência, foi possível armazenar e analisar as conexões entre os usuários, automatizar cálculos e compreender como a estrutura de uma rede pode mudar conforme novos participantes e amizades são adicionados.

A atividade também demonstrou como os grafos podem ser utilizados em sistemas de recomendação de amizades, considerando conexões em comum entre usuários, sempre levando em consideração a importância da privacidade e da proteção dos dados pessoais.

Projeto acadêmico desenvolvido como atividade prática de Estrutura de Dados.
