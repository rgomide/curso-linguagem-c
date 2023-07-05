# Introdução

Um programa em C consiste de funções e pelo menos uma delas é definida de forma obrigatória, a função `main`. Essa é a função principal, no qual a execução de todos os programas são iniciadas a partir dela. As chaves `{` e `}` servem para delimitar um bloco de instruções.

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
| `char`          | 1 byte  | -128 a +127               |
| `int`           | 2 bytes | -32768 a +32767           |
| `float`         | 4 bytes | 3.4e-38 a 3.4e+38         |
| `double`        | 8 bytes | 1.7e-308 a 1.7e+308       |
| `void`          | nenhum  | nenhuma                   |
| `unsigned char` | 1 byte  | 0 a 255                   |
| `unsigned int`  | 2 bytes | 0 a 65535                 |
| `long int`      | 4 bytes | -2147483648 a +2147483647 |

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
|       `%c`      | um único caracter                                  |
|   `%o`, `%d`, `%x`  | um número inteiro em octal, decimal ou hexadecimal |
|       `%u`      | um número inteiro em base decimal sem sinal        |
|      `%ld`      | um número inteiro longo em case decimal            |
|    `%f`, `%lf`    | um número real de precisão simples ou dupla        |
|       `%s`      | uma cadeia de caracteres (string)                  |

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
| `\n`                    | quebra de linha                   |
| `\t`                    | tabulação                         |
| `\”`                    | exibe uma única aspa              |
| `\’`                    | exibe um único apóstrofo          |
| `\\`                    | exibe uma única barra invertida   |
|           `%s`          | uma cadeia de caracteres (string) |

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
|     `+`    | soma de dois números quaisquer            |
|     `-`    | diferença entre dois números quaisquer    |
|     `*`    | produto de dois números quaisquer         |
|     `/`    | quociente da divisão de dois números      |
|     `%`    | resto da divisão de dois números inteiros |

Os operadores de divisão e de resto merecem uma atenção especial:

- Divisão: o operador fornece um resultado inteiro apenas quando ambos os operandos são inteiros. Por exemplo, `7 / 2 => 3` e `7.0 / 2 => 3.5`.
- Resto: o operador de resto somente pode ser utilizado com operandos inteiros. Por exemplo, `7 % 2 => 1` e `7.0 % 2 => erro`.

## Exercícios

1. Faça um algoritmo para calcular a área de uma circunferência, considerando a fórmula `ÁREA = π * RAIO²`. Utilize as variáveis `AREA` e `RAIO`, a constante `π (pi = 3,14159)` e os operadores aritméticos de multiplicação.

2. Faça um algoritmo que calcule a área de um triângulo, considerando a fórmula `Área = (base * altura) / 2`. Utilize as variáveis `AREA`, `BASE` e `ALTURA` e os operadores aritméticos de multiplicação e divisão.

3. Faça um algoritmo que:  
   - Leia dois números de ponto flutuante;
   - Efetue a adição dos dois valores; 
   - Efetue a média dos dois valores;
   - Apresente os valores calculados.

4. Faça um algoritmo que:  
   - Obtenha o valor para a variável `HT` (horas trabalhadas no mês);  
   - Obtenha o valor para a variável `VH` (valor hora trabalhada):  
   - Obtenha o valor para a variável `PD` (percentual de desconto);
   - Calcule o salário bruto: `SB = HT * VH`;  
   - Calcule o total de desconto: `TD = (PD/100)*SB`;  
   - Calcule o salário líquido: `SL = SB – TD`;  
   - Apresente os valores de: Horas trabalhadas, Salário Bruto, Desconto e Salário Líquido.

5. Faça um algoritmo que leia uma temperatura em graus Celsius e apresente-a convertida em graus Fahrenheit. A fórmula de conversão é: `F = (9 * C + 160) / 5`, na qual F é a temperatura em Fahrenheit e C é a temperatura em Celsius.

6. Faça um algoritmo que leia uma temperatura em Fahrenheit e a apresente convertida em graus Celsius. A fórmula de conversão é `C = (F – 32) * (5 / 9)`, na qual F é a temperatura em Fahrenheit e C é a temperatura em Celsius.

7. Faça um algoritmo que leia dois valores para as variáveis A e B e efetue a troca dos valores de forma que a variável A passe a possuir o valor da variável B e a variável B passe a possuir o valor da variável A. Apresente os valores trocados.

8. Considere a seguinte situação: descontam-se inicialmente 10% do salário bruto do trabalhador como contribuição à previdência social. Após esse desconto, há um outro desconto de 5% sobre o valor restante do salário bruto, a título de um determinado imposto. Faça um algoritmo que leia o salário bruto de um cidadão e imprima o seu salário líquido.

9. Faça um algoritmo que calcule a quantidade de litros de combustível gasta em uma viagem, utilizando um automóvel que faz 12 Km por litro. Para obter o cálculo, o usuário deve fornecer o tempo gasto na viagem e a velocidade média durante ela. Desta forma, será possível obter a distância percorrida com a fórmula `DISTANCIA = TEMPO * VELOCIDADE`. Tendo o valor da distância, basta calcular a quantidade de litros de combustível utilizada na viagem com a fórmula: `LITROS_USADOS = DISTANCIA / 12`. O programa deve apresentar os valores da velocidade média, tempo gasto na viagem, a distância percorrida e a quantidade de litros utilizada na viagem.

10. Faça um algoritmo que leia um valor inteiro e apresente os resultados do quadrado e do cubo do valor lido.

11. Dado um número de três algarismos `N = CDU` (onde C é o algarismo das centenas, D é o algarismo das dezenas e U o algarismo das unidades), considere o número M constituído pelos algarismos de N em ordem inversa, isto é, `M = UDC`. Gerar M a partir de N (p.ex.: N = 123 -> M = 321).

12. Suponha que uma escola utilize, como código de matrícula, um número inteiro no formato `AASDDD`, onde: 
    - Os dois primeiros dígitos, representados pela letra A, são os dois últimos algarismos do ano da matrícula; 
    - O terceiro dígito, representado pela letra S, vale 1 ou 2, conforme o aluno tenha se matriculado no 1º ou 2º semestre; 
    - Os três últimos dígitos, representados pela letra D, correspondem à ordem da matrícula do aluno, no semestre e no ano em questão.
    - Crie um algoritmo que leia o número de matrícula de um aluno e imprima o ano e o semestre em que ele foi matriculado.

[Voltar](../)