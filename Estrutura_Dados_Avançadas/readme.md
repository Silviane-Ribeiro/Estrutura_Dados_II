# 🧩 Jogo Didático de HeapSort

Projeto desenvolvido em grupo para a disciplina de **Estruturas de Dados II**, do curso de **Ciência da Computação**.
Os arquivos estão no diretório acessado pelo link [Jogo Didático HeapSort](https://github.com/Nogueira-Amanda/Estrutura_Dados_II/tree/main/Serious%20Games%20-%20Guia%20Avan%C3%A7ado).\
O projeto consiste em um **jogo educativo executado no terminal**, desenvolvido em Python, com o objetivo de ensinar o funcionamento do algoritmo **HeapSort** por meio da participação ativa do estudante durante as etapas de construção da `max-heap` e ordenação do vetor.

---

## 🎯 Objetivo

O objetivo do projeto é transformar o estudo do HeapSort em uma atividade prática, na qual o jogador precisa identificar e executar corretamente as trocas necessárias para manter a propriedade da `max-heap` e realizar a ordenação dos elementos.

Dessa forma, o estudante não apenas observa a execução do algoritmo, mas precisa tomar as decisões de cada etapa e recebe feedback imediato sobre suas escolhas.

---

## 📚 Contexto do Projeto

O projeto foi desenvolvido a partir da análise de um modelo existente denominado **Sortia 2.0**, um jogo de ordenação voltado ao ensino de Estruturas de Dados e do algoritmo HeapSort. O jogo original pode ser encontrado em [Sortia 2.0](https://sol.sbc.org.br/index.php/sbsi/article/view/6007)

O modelo analisado apresenta o HeapSort por meio da manipulação de um vetor interpretado como uma heap. Entretanto, durante a análise realizada pelo grupo, foi identificada uma limitação na representação da estrutura: a árvore hierárquica não era apresentada de forma visual, ficando restrita à representação do vetor.

Como não foi possível obter acesso ao código original do Sortia, foi desenvolvida uma nova versão do jogo diretamente em Python, executada pelo terminal.

A proposta preserva a ideia de **aprendizagem ativa**, permitindo que o estudante participe diretamente das operações realizadas pelo HeapSort.

---

## ⚙️ Funcionamento

O jogo é dividido em duas etapas principais:

### 1. Construção da Max-Heap

Inicialmente, o jogador fornece os valores que serão utilizados no vetor.

O programa pode:

* gerar automaticamente um vetor com números aleatórios; ou
* permitir que o jogador informe seus próprios valores.

Em seguida, o programa percorre os nós da heap de baixo para cima e solicita ao jogador que realize as trocas necessárias para restaurar a propriedade da `max-heap`.

Na `max-heap`:

> Todo nó pai deve possuir valor maior ou igual aos seus filhos.

A representação da heap utiliza um vetor. Para um nó de índice `i`:

```text
Filho esquerdo = 2i + 1
Filho direito  = 2i + 2
```

---

### 2. Ordenação pelo HeapSort

Depois que a `max-heap` é construída, começa a etapa de ordenação.

O maior elemento está localizado na raiz da heap, no índice `0`.

A cada rodada:

1. O jogador identifica a troca necessária entre a raiz e o último elemento da região ainda não ordenada.
2. O maior elemento é colocado em sua posição definitiva.
3. A região ativa da heap é reduzida.
4. A propriedade da `max-heap` é restaurada por meio de novas trocas.
5. O processo continua até que todos os elementos estejam ordenados.

Durante a execução, o programa mostra a separação entre:

```text
Heap ativa
Elementos já ordenados
```

Também é apresentada uma representação lógica da heap por níveis, facilitando a compreensão da relação entre o vetor e a estrutura hierárquica.

---

## 🕹️ Mecânica do Jogo

O jogador deve informar os índices dos elementos que precisam ser trocados.

Por exemplo:

```text
Digite os índices que devem ser trocados:
1 4
```

O programa verifica se a troca escolhida está correta.

### ✅ Acerto

Quando a troca está correta:

* o vetor é atualizado;
* o jogador recebe feedback positivo;
* um acerto é contabilizado;
* a execução continua.

### ❌ Erro

Quando a troca está incorreta:

* o jogador recebe uma mensagem explicando que a troca não restaura a propriedade da heap;
* um erro é contabilizado;
* o jogador pode tentar novamente.

### 💡 Dicas

O jogador também pode utilizar a opção:

```text
dica
```

A utilização de uma dica ajuda na resolução da etapa, mas é contabilizada no placar final.

---

## 🏆 Sistema de Pontuação

O jogo possui um sistema simples de pontuação baseado no desempenho do jogador.

A pontuação é calculada da seguinte maneira:

```text
Pontos = (Acertos × 10) - (Erros × 2) - Dicas
```

A pontuação nunca pode ser menor que zero.

Ao final da partida, o programa apresenta:

* quantidade de acertos;
* quantidade de erros;
* quantidade de dicas utilizadas;
* pontuação final;
* vetor original;
* vetor ordenado.

---

## 🧠 Conceitos de Estruturas de Dados

O projeto utiliza e demonstra conceitos fundamentais relacionados ao HeapSort e às heaps:

* Vetores;
* Índices;
* Árvores binárias representadas por vetores;
* Max-heap;
* Relação entre pai e filhos;
* Construção de uma heap;
* Operação de descida (`sift-down`);
* Trocas de elementos;
* Ordenação;
* Região ativa e região já ordenada;
* Participação interativa na execução do algoritmo.

---

## 🐍 Tecnologias Utilizadas

* **Python 3**
* Terminal/Console
* `random`
* `dataclasses`

Não são utilizadas bibliotecas externas.

---

## ▶️ Como Executar

O projeto foi desenvolvido e disponibilizado em formato **Jupyter Notebook (`.ipynb`)**, utilizando o **Google Colab**.

### ☁️ Executando pelo Google Colab

A forma recomendada de executar o projeto é pelo Google Colab:

1. Baixe o arquivo `Jogo HeapSort-Sortia.ipynb` deste repositório.
2. Acesse o [Google Colab](https://colab.research.google.com/).
3. Abra o arquivo `.ipynb` no Colab.
4. Execute as células do notebook na ordem apresentada.
5. Siga as instruções exibidas para interagir com o jogo.

### 💻 Executando localmente

O arquivo também pode ser aberto em um ambiente compatível com **Jupyter Notebook**, como o JupyterLab ou o Visual Studio Code com suporte a notebooks.

Após abrir o arquivo `Jogo HeapSort-Sortia.ipynb`, execute as células na ordem apresentada e siga as instruções exibidas no terminal/saída da célula.

### 🎮 Início do jogo

Ao iniciar o programa, o jogador poderá escolher entre:

```text
1 — Usar números aleatórios
2 — Digitar os números
```

Depois disso, o jogo conduzirá o jogador pelas etapas de construção da `max-heap` e execução do HeapSort.

## 📁 Arquivos do Projeto

```text
📦 Projeto HeapSort
 ├── 📄 Jogo Heapsort_Sortia.ipynd
 ├── 📄 Guia de Atividade Prática do Estudante - Design de Jogos sobre Árvores Avançadas.pdf
 └── 📄 README.md
```

### `heapsort.py`

Arquivo principal do projeto. Contém toda a implementação do jogo, incluindo:

* criação e validação da heap;
* representação da árvore;
* interação com o jogador;
* validação das trocas;
* sistema de dicas;
* sistema de pontuação;
* construção da `max-heap`;
* execução manual do HeapSort;
* verificação final da ordenação.

### `Guia de Atividade Prática do Estudante`

Documento utilizado como referência para o desenvolvimento da atividade acadêmica, contendo as orientações, o diagnóstico do modelo reutilizado, a proposta do projeto e o mapeamento dos conceitos de Estruturas de Dados para as mecânicas do jogo.

---

## 👥 Integrantes

* [Amanda de Souza Nogueira](https://github.com/Nogueira-Amanda/Estrutura_Dados_II/tree/main)
* Silviane Souza
* [Rodrigo Nunes](https://github.com/rodrigonunx-spec/Estrutura_de_Dados_II)
* [Liz Cristina](https://github.com/RyuuBatataa/Estrutura_de_Dados_II)

**Disciplina:** Estruturas de Dados II
**Curso:** Ciência da Computação
**Data:** 18/09/2026

---

## 📌 Proposta Educacional

O projeto busca aplicar o conceito de **aprender fazendo**, transformando as operações do HeapSort em decisões que precisam ser tomadas pelo jogador.

Em vez de simplesmente executar o algoritmo automaticamente, o programa solicita que o estudante identifique as trocas e acompanhe as alterações realizadas na estrutura.

Assim, o jogo funciona como uma ferramenta de apoio ao aprendizado, permi
