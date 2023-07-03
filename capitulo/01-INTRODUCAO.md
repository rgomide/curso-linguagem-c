# Introdução

Um programa em C consiste de funções e pelo menos uma delas é definida de forma obrigatória, a função main. Essa é a função principal, no qual a execução de todos os programas são iniciadas a partir dela. As chaves `{` e `}` servem para delimitar um bloco de instruções.

## Sumário

- [Operador de atribuição](#operador-de-atribuição)
- [Tipos de Dados](#tipos-de-dados)
- [Declaração de variáveis](#declaração-de-variáveis)
- [Entrada e saída de dados](#entrada-e-saída-de-dados)
- [Operadores aritméticos](#operadores-aritméticos)
- [Exercícios](#exercícios)

## Operador de atribuição

O operador de atribuição tem como finalidade modificar o valor de uma variável. Na linguagem C o operador de atribuição é o sinal de igual `=`.

## Tipos de Dados

Na linguagem C utiliza-se cinco tipos de dados:

|      Tipo     |  Espaço |           Escala          |
|:-------------:|:-------:|:-------------------------:|
| char          | 1 byte  | -128 a +127               |
| int           | 2 bytes | -32768 a +32767           |
| float         | 4 bytes | 3.4e-38 a 3.4e+38         |
| double        | 8 bytes | 1.7e-308 a 1.7e+308       |
| void          | nenhum  | nenhuma                   |
| unsigned char | 1 byte  | 0 a 255                   |
| unsigned int  | 2 bytes | 0 a 65535                 |
| long int      | 4 bytes | -2147483648 a +2147483647 |

## Declaração de variáveis

A declaração de uma variável consiste em um tipo e um identificador. O tipo determina o espaço de memória alocado a ela e o identificador permite a referência a ela no decorrer do programa. As variáveis devem ser declaradas antes de serem usadas, logo no início do bloco de instruções.

Todo identificador de variável deve iniciar-se com letra e ser composto por letras, dígitos e sublinhas.

```c
char tecla, opcao;
int a, b;
float desconto, salario;
```

## Entrada e saída de dados

### A função scanf()

A função `scanf()` captura um valor a partir da leitura do teclado e armazena em uma variável. Sua sintaxe consiste em uma cadeia de formatação e uma lista de argumentos que representam as variáveis.

Para a leitura de uma variável, utiliza-se um especificador referente ao tipo da variável. A tabela a seguir apresenta a relação dos especificadores disponíveis na linguagem C:

| Especificador |                     Representa                     |
|:-------------:|:--------------------------------------------------:|
|       %c      | um único caracter                                  |
|   %o, %d, %x  | um número inteiro em octal, decimal ou hexadecimal |
|       %u      | um número inteiro em base decimal sem sinal        |
|      %ld      | um número inteiro longo em case decimal            |
|    %f, %lf    | um número real de precisão simples ou dupla        |
|       %s      | uma cadeia de caracteres (string)                  |

Ao interpretar um comando `scanf()`, o fluxo de execução de um programa fica em espera até que uma informação seja entrada via teclado. A função `scanf()` pode ser utilizada para obter a leitura de uma ou mais variáveis. O exemplo a seguir mostra essas duas situações:

```c
#include <stdio.h>

int main(void) {
 // DECLARAÇÃO DAS VARIÁVEIS
 int a, b;
 float c;
 // LEITURA DA VARIÁVEL a
 scanf("%d", &a);
 // LEITURA DAS VARIÁVEIS b E c
 scanf("%d %f", &b, &c);
 printf("%d %d %f", a, b, c);
}
```

O operador `&` informa o endereço de memória em que uma variável foi alocada.

_Obs.: na linguagem C o operador // significa comentário de linha. As linhas marcadas com esse operador são ignoradas pelo compilador._

### A função printf()

A função `printf()` permite exibir um texto de acordo com alguma formatação. A sintaxe da função é:

```c
printf("formatação", n1, n2, n3, ..., n);
```

A cadeia de formatação pode conter texto e informações de variáveis. A representação das variáveis segue o esquema de especificação de acordo com o seu tipo.

```c
#include <stdio.h>

int main(void) {
 int a = 3;
 float b = 4.5;
 char c = 'c';
 printf("Variável a = %d ", a);
 printf("Variável b = %f ", b);
 printf("Variável c = %c ", c);
}
```

Além disso, é possível utilizar caracteres especiais com a finalidade de organizar a saída de texto, como por exemplo, quebra de linha, tabulação, entre outros. A tabela a seguir apresenta os principais caracteres de controle:

| Caractere de controle |               Efeito              |
|:---------------------:|:---------------------------------:|
| \n                    | quebra de linha                   |
| \t                    | tabulação                         |
| \”                    | exibe uma única aspa              |
| \’                    | exibe um único apóstrofo          |
| \\                    | exibe uma única barra invertida   |
|           %s          | uma cadeia de caracteres (string) |

O exemplo a seguir mostra algumas situações para a utilização dos caracteres de controle:

```c
#include <stdio.h>

int main(void) {
 int a = 3; float b = 4.5; char c = 'c';
 printf("Variável a = %d\nVariável b = %f\nVariável c = %c", a, b, c); 
 printf("\nValores\n\ta = %d\n\tb = %f\n\tc = %c", a, b, c);
}
```

## Operadores aritméticos

A linguagem C oferece operadores para as quatro operações aritméticas e um operador para calcular o resto entre a divisão de dois números.

| Operador |                 Resultado                 |
|:--------:|:-----------------------------------------:|
|     +    | soma de dois números quaisquer            |
|     -    | diferença entre dois números quaisquer    |
|     *    | produto de dois números quaisquer         |
|     /    | quociente da divisão de dois números      |
|     %    | resto da divisão de dois números inteiros |

Os operadores de divisão e de resto merecem uma atenção especial:

- Divisão: o operador fornece um resultado inteiro apenas quando ambos os operandos são inteiros. Por exemplo, `7 / 2 => 3` e `7.0 / 2 => 3.5`.
- Resto: o operador de resto somente pode ser utilizado com operandos inteiros. Por exemplo, `7 % 2 => 1` e `7.0 % 2 => erro`.

## Exercícios