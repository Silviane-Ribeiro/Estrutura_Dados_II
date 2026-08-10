#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <time.h>

float vetor[500];
int Qtd = 0;

int imprimeMenu() {

    printf("\n ===== EXERCICIO DE ORDENACAO =====   ");
    printf("\n  1: Preencher o vetor                ");
    printf("\n  2: Limpar o vetor                   ");
    printf("\n  3: Imprimir o vetor                 ");
    printf("\n  4: Ordenar Bubble Sort              ");
    printf("\n  5: Ordenar Selection Sort           ");
    printf("\n  6: Ordenar Insertion Sort           ");
    printf("\n  7: Preencher Vetor Aleatoriamente = ");
    printf("\n  8: Sair                             ");
    printf("\n ==================================   ");
    printf("\n Informe a opcao desejada:            ");

    int resposta;
    scanf("%i", &resposta);
    return resposta;
}

void VetorAleatorio(int Tamanho){
    for(int i = 0; i < Tamanho; i++)
        vetor[i] = rand() % 100;

    printf("\n %i numeros gerados com sucesso!", Tamanho);
    Qtd = Tamanho;
    getch();
}

void limparVetor() {
    Qtd = 0;
    printf("\nVetor limpo com sucesso!");
    getch();
}

void bubbleSort() {
    float aux;

    for (int i = 0; i < Qtd - 1; i++) {
        for (int j = 0; j < Qtd - 1 - i; j++) {
            if (vetor[j] > vetor[j + 1]) {
                aux = vetor[j];
                vetor[j] = vetor[j + 1];
                vetor[j + 1] = aux;
            }
        }
    }
}

void selectionSort() {
    float aux;

    for (int i = 0; i < Qtd - 1; i++) {
        for (int j = i + 1; j < Qtd; j++) {
            if (vetor[j] < vetor[i]) {
                aux = vetor[j];
                vetor[j] = vetor[i];
                vetor[i] = aux;
            }
        }
    }
}

void insertionSort() {
    float aux;
    int j;

    for (int i = 1; i < Qtd; i++) {
        aux = vetor[i];
        j = i - 1;

        while (j >= 0 && vetor[j] > aux) {
            vetor[j + 1] = vetor[j];
            j--;
        }

        vetor[j + 1] = aux;
    }
}

void imprimirVetor() {
    printf("\nDados do Vetor:\n");

    for (int i = 0; i < Qtd; i++) {
        printf("%.2f, ", vetor[i]);
    }

    getch();
}

int main() {
    char menu;
    int resposta;
    int tamanho;

    srand(time(NULL));

    do {
        resposta = imprimeMenu();

        if (resposta == 1) {
            do {
                printf("\nInsira o %i. valor no vetor: ", Qtd + 1);
                scanf("%f", &vetor[Qtd]);
                Qtd++;

                printf("Deseja inserir mais um valor? (S/N): ");
                scanf(" %c", &menu);

            } while (menu == 'S' || menu == 's');
        }

        else if (resposta == 2) {
            limparVetor();
        }

        else if (resposta == 3) {
            imprimirVetor();
        }

        else if (resposta == 4) {
            bubbleSort();
            printf("\nVetor ordenado com Bubble Sort:\n");
            imprimirVetor();
        }

        else if (resposta == 5) {
            selectionSort();
            printf("\nVetor ordenado com Selection Sort:\n");
            imprimirVetor();
        }

        else if (resposta == 6) {
            insertionSort();
            printf("\nVetor ordenado com Insertion Sort:\n");
            imprimirVetor();
        }

        else if (resposta == 7) {
            printf("\nInforme quantos numeros deseja gerar: ");
            scanf("%i", &tamanho);

            VetorAleatorio(tamanho);
        }

    } while (resposta != 8);

    return 0;
}
_________________________________________________________________________________________________________________________________________
# 🔢 Exercício de Ordenação de Vetores em C

Projeto desenvolvido durante a graduação em **Ciência da Computação** para praticar conceitos de **vetores, funções, estruturas de repetição e algoritmos de ordenação** utilizando a linguagem C.

O programa permite criar e manipular um vetor de números e realizar a ordenação utilizando diferentes algoritmos.

## 🎯 Objetivo

O objetivo deste projeto é estudar e comparar, na prática, diferentes métodos de ordenação de dados.

O programa disponibiliza três algoritmos de ordenação:

- 🔵 Bubble Sort
- 🟢 Selection Sort
- 🟠 Insertion Sort

Além disso, permite preencher o vetor manualmente ou gerar valores aleatórios.

## 🛠️ Tecnologias utilizadas

- **Linguagem:** C
- **Bibliotecas:**
  - `stdio.h`
  - `conio.h`
  - `stdlib.h`
  - `time.h`

## 📌 Funcionalidades

O programa possui um menu interativo com as seguintes opções:

| Opção | Funcionalidade |
|------:|----------------|
| 1 | Preencher o vetor manualmente |
| 2 | Limpar o vetor |
| 3 | Imprimir o vetor |
| 4 | Ordenar utilizando Bubble Sort |
| 5 | Ordenar utilizando Selection Sort |
| 6 | Ordenar utilizando Insertion Sort |
| 7 | Preencher o vetor aleatoriamente |
| 8 | Sair do programa |

## 📚 Conceitos praticados

Neste projeto foram trabalhados diversos conceitos fundamentais da programação em C:

- Variáveis
- Tipos de dados
- Vetores
- Funções
- Parâmetros
- Retorno de funções
- Estruturas `if` e `else`
- Estruturas `for`
- Estruturas `while`
- Estrutura `do while`
- Entrada e saída de dados
- Manipulação de arrays
- Variáveis globais
- Geração de números aleatórios
- Troca de valores entre posições do vetor
- Algoritmos de ordenação

# 🔵 Bubble Sort

O **Bubble Sort** compara elementos que estão lado a lado no vetor.

Quando o elemento da esquerda é maior que o elemento da direita, os dois valores são trocados.

O processo é repetido várias vezes até que o vetor esteja ordenado.

### Exemplo

Vetor inicial:

```text
5  3  8  1
