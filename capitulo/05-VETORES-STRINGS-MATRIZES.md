# Vetores, Strings e Matrizes

## Sumário

- [Vetores](#vetores)
- [Strings](#strings)
  - [Leitura e Escrita de Strings](#leitura-e-escrita-de-strings)
  - [Manipulação de Strings](#manipulação-de-strings)
- [Matrizes](#matrizes)
- [Exercícios](#exercícios)
  - [Vetores](#vetores-1)
  - [Strings](#strings-1)
  - [Matrizes](#matrizes-1)
## Vetores

Um vetor é uma coleção de variáveis de um mesmo tipo, que compartilham o mesmo nome e que ocupam posições consecutivas de memória. Cada uma dessas variáveis denomina-se elemento e é identificada por um índice. Se v é um vetor com n posições, seus elementos são `v[0], v[1], v[2], …, v[n - 1]`. A Figura a seguir mostra a estrutura de um vetor e os seus elementos.

Na linguagem C os vetores são sempre indexados a partir da posição zero e o último elemento de um vetor de tamanho n ocupa a posição `n - 1` do vetor. Para criar um vetor, declare uma variável com o sufixo `[n]`, sendo n uma constante indicando o número de elementos a serem alocados no vetor.

O exemplo a seguir mostra a declaração de um vetor `v` de tamanho cinco. Assim, é feita a leitura das cinco posições e em seguida é realizado o cálculo do somatório dos valores armazenados nesse vetor.

```C
#include <stdio.h>

int main(void) {
 int v[5], c, soma = 0;
 for (c = 0; c < 5; c++) {
   printf("Informe um valor para a posição %d: ", c);
   scanf("%d", &v[c]);
   soma += v[c];
 }
 printf("O valor do somatório dos elementos é: %d", soma);
}
```

## Strings

### Leitura e Escrita de Strings

### Manipulação de Strings

## Matrizes

## Exercícios

### Vetores

### Strings

### Matrizes



[Voltar](../)