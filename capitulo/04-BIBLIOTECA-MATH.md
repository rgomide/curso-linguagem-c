# A biblioteca math.h

A biblioteca `math.h` fornece um conjunto de funções matemáticas além dos operadores aritméticos, tais como funções trigonométricas, hiperbólicas, logaritmos, potência e arredondamentos. Todas as funções da biblioteca math.h retornam um valor do tipo ponto flutuante (`double`).

A tabela a seguir mostra as principais funções presentes na biblioteca `math.h`:

|       Função       |           Descrição          |
|:-------------------:|:----------------------------:|
| floor( )            | arredonda o valor para baixo |
| ceil( )             | arredonda o valor para cima  |
| sqrt( )             | calcula raiz quadrada        |
| pow(base, expoente) | calcula a potência           |
| sin( )              | seno                         |
| cos( )              | cosseno                      |
| tan( )              | tangente                     |
| log( )              | logaritmo natural            |
| log10( )            | logaritmo base 10            |

O exemplo a seguir apresenta o uso dessas funções:

```C
#include <stdio.h>
#include <math.h> //necessária para usar as funções matemáticas

int main ()
{
 float x = 9.75;
 float arredonda_pbaixo = 0.0;
 float arredonda_pcima = 0.0;
 float raiz_quadrada = 0.0;
 float potencia = 0;
 float seno = 0;
 float cosseno = 0;
 float tangente = 0;
 float logaritmo_natural = 0;
 float logaritmo_xbase10 = 0;
 
 printf("\n********* Utilizando a biblioteca math.h ***********\n\n");
 printf("\nFuncoes de arredondamento\n\n");
 
 printf("Valor original de x = %f\n",x);
 
 arredonda_pbaixo = floor(x);
 printf("Valor aproximado para baixo %f \n", arredonda_pbaixo );
 
 arredonda_pcima = ceil(x);
 printf("Valor aproximado para cima %f \n", arredonda_pcima);
 
 printf("\n----------------------------------------------------\n\n");
 printf("\nFuncoes de raiz e potenciacao \n\n");
 
 printf("Valor original de x = %lf\n",x);

 raiz_quadrada = sqrt(x);
 printf("Valor da raiz quadrada %f \n",raiz_quadrada);
 
 x = ceil(x); //arredondando o x para cima, x passa a valer 10
 
 potencia = pow(x,2); //elevando o valor de x ao quadrado
 printf("Valor de %.2lf ao quadrado %.2f \n",x,potencia);

 printf("\n----------------------------------------------------\n\n");
 printf("\nFuncoes trigonometricas\n\n");
 
 x = 0; //atribuindo zero em x para fazer os cálculos trigonométricos
 
 seno = sin(x);
 printf("Valor de seno de %.2f = %.2f \n",x,seno);
 
 cosseno = cos(x);
 printf("Valor de cosseno de %.2f = %.2f \n",x,cosseno);
 
 tangente = tan(x);
 printf("Valor de tangente de %.2f = %.2f \n\n",x,tangente);
 
 printf("\n----------------------------------------------------\n\n");
 printf("\nFuncoes logaritmicas\n\n");
 
 x = 2.718282;
 
 logaritmo_natural = log(x);
 printf("Logaritmo natural de x %.2f = %.2f \n",x,logaritmo_natural);
 
 x = 10;
 logaritmo_xbase10 = log10(x);
 printf("Logaritmo de x na base 10 %.2f = %.2f \n",x,logaritmo_xbase10);
 
 printf("\n----------------------------------------------------\n\n");
}

```

[Voltar](../)