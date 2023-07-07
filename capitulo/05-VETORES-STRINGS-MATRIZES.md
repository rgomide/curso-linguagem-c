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

<img src="./assets/img/vetor.drawio.png" width="550"/>

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

Na linguagem C uma String não é um tipo de dados básico. Uma string é uma série de caracteres terminada com um caractere representado por `'\0'`. Um vetor de caracteres é utilizado para representar uma string. Essa representação possibilita que os caracteres que formam um string sejam acessados individualmente.

A Figura a seguir mostra a representação de uma string com o valor `verde e amarelo`.

<img src="./assets/img/string.drawio.png" width="550"/>

Devido à necessidade do `'\0'`, os vetores que armazenam strings devem ter sempre uma posição a mais do que o número de caracteres a serem armazenados.

### Leitura e Escrita de Strings

Para ler o valor de uma string utiliza-se a função `fgets(variável, tamanho, stdin)` da biblioteca `stdlib.h`. A exibição de uma string pode ser feita a partir do especificador `%s` na função `printf()`. O exemplo de código a seguir mostra as ações de declaração, leitura e escrita de uma string de tamanho 20.

```C
#include <stdio.h>

int main(void) {
 char p[20];
 printf("Informe uma cadeia de caracteres: ");
 fgets(p, 20, stdin);
 printf("A string informada foi: %s", p);
}
```

### Manipulação de Strings

Como a string não é um tipo básico da linguagem C, operações como atribuição e comparação não podem ser feitas diretamente com os operadores disponíveis. A partir dessa premissa a linguagem C possui uma biblioteca própria para realizar as operações em strings. Essa biblioteca é a `string.h`.

| Função                        | Significado                                                                    |
|-------------------------------|--------------------------------------------------------------------------------|
| `fgets(string, tamanho, stdin)` | Lê uma string                                                                  |
| `strcmp(string1, string2)`      | Compara duas strings. Se `strcmp(string1, string2) == 0`, então elas são iguais. |
| `strcpy(destino, origem)`       | Copia uma string para outra                                                    |
| `strlen(string)`                | Calcula o tamanho da string                                                    |
| `strcat(destino, origem)`       | Concatena duas strings                                                         |
| `strtok(string, “\n”)`          | Remove o caractere de nova linha                                               |

O código a seguir mostra exemplos de uso para as funções listadas na tabela anterior.

```C
#include <stdio.h>
#include <string.h>

int main(void) {
 char x[20], y[20];
 int i;
 printf("Informe uma string: ");
 fgets(x, 20, stdin); 
 // Compara se a string digitada é igual a "sim"
 if (strcmp(x, "sim")) {
   printf("A string digitada é %s", x);
 }
 // Copiar uma string para outra
 strcpy(y, x);
 printf("String copiada: %s", y);
 // Obter o tamanho da string
 printf("Tamanho da string: %ld", strlen(x));
 // Concatenar string
 strcat(x, " teste");
 printf("%s", x);
}
```

## Matrizes

Uma matriz é uma coleção homogênea bidimensional no qual os elementos são distribuídos em linhas e colunas. Se `A` é uma matriz `m x n`, então as suas linhas são indexadas de `0` a `m - 1` e as suas colunas de `0` a `n - 1`.	Para acessar um elemento de `A`, utiliza-se `A[i][j]`, sendo que `i` é o índice da linha e `j` o índice da coluna que o elemento ocupa.

O código do exemplo a seguir mostra a declaração de uma matriz `3 x 2`, a leitura e a impressão de todos os elementos dessa matriz:

```C
#include <stdio.h>

int main(void) {
 int a[3][2];
 int i, j;
 for (i = 0; i < 3; i++) {
   for (j = 0; j < 2; j++) {
     printf("a[%d][%d]: ", i, j);
     scanf("%d", &a[i][j]);
   }
 }
 for (i = 0; i < 3; i++) {
   for (j = 0; j < 2; j++) {
     printf("%d\t", a[i][j]);     
   }
   printf("\n");
 }
}
```

## Exercícios

### Vetores

### Strings

### Matrizes



[Voltar](../)