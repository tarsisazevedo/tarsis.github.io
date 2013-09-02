---
layout: post
title: Aprendendo C - formatação do printf
tags:
- C
- programming
- formatacao printf
- aprendendo c
- tutorial
---
<style type="text/css">

table {
  max-width: 100%;
  border-collapse: collapse;
  border-spacing: 0;
}
.table {
  width: 100%;
  margin-bottom: 18px;
}
.table th, .table td {
  padding: 8px;
  line-height: 18px;
  text-align: left;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table th {
  font-weight: bold;
}
.table thead th {
  vertical-align: bottom;
}
.table thead:first-child tr th, .table thead:first-child tr td {
  border-top: 0;
}
.table tbody + tbody {
  border-top: 2px solid #ddd;
}
.table-condensed th, .table-condensed td {
  padding: 4px 5px;
}
.table-bordered {
  border: 1px solid #ddd;
  border-collapse: separate;
  *border-collapse: collapsed;
  -webkit-border-radius: 4px;
  -moz-border-radius: 4px;
  border-radius: 4px;
}
.table-bordered th + th,
.table-bordered td + td,
.table-bordered th + td,
.table-bordered td + th {
  border-left: 1px solid #ddd;
}
.table-bordered thead:first-child tr:first-child th, .table-bordered tbody:first-child tr:first-child th, .table-bordered tbody:first-child tr:first-child td {
  border-top: 0;
}
.table-bordered thead:first-child tr:first-child th:first-child, .table-bordered tbody:first-child tr:first-child td:first-child {
  -webkit-border-radius: 4px 0 0 0;
  -moz-border-radius: 4px 0 0 0;
  border-radius: 4px 0 0 0;
}
.table-bordered thead:first-child tr:first-child th:last-child, .table-bordered tbody:first-child tr:first-child td:last-child {
  -webkit-border-radius: 0 4px 0 0;
  -moz-border-radius: 0 4px 0 0;
  border-radius: 0 4px 0 0;
}
.table-bordered thead:last-child tr:last-child th:first-child, .table-bordered tbody:last-child tr:last-child td:first-child {
  -webkit-border-radius: 0 0 0 4px;
  -moz-border-radius: 0 0 0 4px;
  border-radius: 0 0 0 4px;
}
.table-bordered thead:last-child tr:last-child th:last-child, .table-bordered tbody:last-child tr:last-child td:last-child {
  -webkit-border-radius: 0 0 4px 0;
  -moz-border-radius: 0 0 4px 0;
  border-radius: 0 0 4px 0;
}
.table-striped tbody tr:nth-child(odd) td, .table-striped tbody tr:nth-child(odd) th {
  background-color: #f9f9f9;
}
.table tbody tr:hover td, .table tbody tr:hover th {
  background-color: #f5f5f5;
}
table .span1 {
  float: none;
  width: 44px;
  margin-left: 0;
}
table .span2 {
  float: none;
  width: 124px;
  margin-left: 0;
}
table .span3 {
  float: none;
  width: 204px;
  margin-left: 0;
}
table .span4 {
  float: none;
  width: 284px;
  margin-left: 0;
}
table .span5 {
  float: none;
  width: 364px;
  margin-left: 0;
}
table .span6 {
  float: none;
  width: 444px;
  margin-left: 0;
}
table .span7 {
  float: none;
  width: 524px;
  margin-left: 0;
}
table .span8 {
  float: none;
  width: 604px;
  margin-left: 0;
}
table .span9 {
  float: none;
  width: 684px;
  margin-left: 0;
}
table .span10 {
  float: none;
  width: 764px;
  margin-left: 0;
}
table .span11 {
  float: none;
  width: 844px;
  margin-left: 0;
}
table .span12 {
  float: none;
  width: 924px;
  margin-left: 0;
}
</style>

Recentemente comecei a aprender C. Sim eu não sei C, não tive na faculdade e sempre senti
falta de saber melhor como as coisas funionavam por dentro do computador,
já que minha maior experiencia em programação é com python, que é uma linguagem de altissimo nivel.

Com C voce trabalha mais perto da maquina, direto com bytes, alocação de memoria, tem que fazer as estruturas de dados.

E pra aprender eu escolhi estudar pelo livro Learn C The Hard Way do Zed Shaw.
É um livro que te instiga a estudar os conceitos por voce mesmo, ensina em cima
de exemplos bem praticos e eficientes, te adiciona ao ecossistema da linguagem, apresentando ferramentas e tecnicas que vao te ajudar a pensar em C.

Uma das coisas que ele me instigou a estudar foi todos os possiveis formatos e
suas variações para o printf, a função que escreve na saida padrão (o print do python).

{% highlight c %}
#include <stdio.h>

int main() {
    printf("%s\n", "Hello World!");
    return 0;
}
{% endhighlight %}

#### output

    Hello World!

> 

### formatando a saida do printf

O printf recebe 2 parametros: uma string com os formatos mapeados e um minimo de valores igual ao mapeado.

{% highlight c %}
#include <stdio.h>

int main() {
    printf("%d %s\n", 1, "Hello again!");
    return 0;
}
{% endhighlight %}

#### output

    1 Hello again!

> 

Esta função é capaz de imprimir diferentes tipos de dados (char, string, int, float, octal, hexa, outros aqui) de acordo com a formatação que voce usar.

{% highlight c %}
#include <stdio.h>

int main() {
    printf("Decimais: %d %ld\n", 1988, 650000L);
    printf("Precedido com espaços em branco: %10d\n", 1988);
    printf("Precedido com zeros: %010d\n", 1988);
    printf("Numeros com base diferente: %d %x %o %#x %#o \n", 100, 100, 100, 100, 100);
    printf("Floats: %4.2f %+.0e %E \n", 3.14554, 3.3214, 3.1234);
    printf("Truque de tamanho: %*d\n", 5, 10);

    return 0;
}
{% endhighlight %}

#### output

    Char: b A
    Decimais: 1988 650000
    Precedido com espaços em branco:       1988
    Precedido com zeros: 0000001988
    Numeros com base diferente: 100 64 144 0x64 0144
    Floats: 3.15 +3e+00 3.123400E+00
    Truque de tamanho:    10
    String simples Oi!

## Tabela de Formatos

    Os formatos seguem o seguinte padrão: %[flags][tamanho][.precisao][quantidade]formato
    Flags, largura, .precisão, tamanho são opcionais.

### Formatos:
<table class="table table-bordered"><tbody><tr><th>Formato</th>
      <th>Saida</th>
      <th>Exemplo</th>
    </tr><tr><td>c</td>
      <td>char</td>
      <td>a</td>
    </tr><tr><td>d ou i</td>
      <td>signed int</td>
      <td>1</td>
    </tr><tr><td>e</td>
      <td>Notação Cientifica usando o caracter e</td>
      <td>3.9265e+2</td>
    </tr><tr><td>E</td>
      <td>Notação Cientifica usando o caracter E</td>
      <td>3.9265E+2</td>
    </tr><tr><td>f</td>
      <td>float</td>
      <td>3.4</td>
    </tr><tr><td>g</td>
      <td>usa o menor numero possivel de f e e</td>
      <td>3.54</td>
    </tr><tr><td>G</td>
      <td>usa o menor numero possivel de f e E</td>
      <td>3.54</td>
    </tr><tr><td>o</td>
      <td>unsigned octal</td>
      <td>610</td>
    </tr><tr><td>s</td>
      <td>string</td>
      <td>Hello World</td>
    </tr><tr><td>u</td>
      <td>unsigned int</td>
      <td>2345</td>
    </tr><tr><td>x</td>
      <td>unsigned hexa</td>
      <td>7fa</td>
    </tr><tr><td>X</td>
      <td>unsigned hexa com letras maiusculas</td>
      <td>7FA</td>
    </tr><tr><td>p</td>
      <td>ponteiro de endereço</td>
      <td>B800:0000</td>
    </tr><tr><td>n</td>
      <td>Nada impresso. O argumento deve ser um ponteiro para um int assinado, onde o número de caracteres escritos até então é armazenado.</td>
      <td></td>
    </tr><tr><td>%</td>
      <td>% seguido de outro % irá printar % na saida</td>
      <td>%</td>
    </tr></tbody></table>

### Flags
<table class="table table-bordered"><tbody><!-- Results table headers --><tr><th>Flag</th>
      <th>Descrição</th>
    </tr><tr><td>-</td>
      <td>Alinhado a esquerda dentro do tamanho definido. Alinhamento a direita é o padrão (veja a tabela de formatação de tamanho).</td>
    </tr><tr><td>+</td>
      <td>Força a o resultado ser mostrado com um simbolo de + ou -. Por padrão, somente numeros negativos são mostrados com -.</td>
    </tr><tr><td>#</td>
      <td>Usado com o, x e X indica que o valor será precedido de 0, 0x ou 0X  respectivamente, para valores diferentes de 0.<br>Usado com e, E e f, força o output para mostrar um ponto decimal mesmo sem numeros depois dele. Por padrão, se nenhum numero estiver depois do ponto decimal ele nao é mostrado.<br>Usado com g e G o resultado é mostrado com zeros a direita.</td>
    </tr><tr><td>0</td>
      <td>Numero 0 é printado ao invés de espaços em branco quando o tamanho é especificado. (veja a tabela de formatação de tamanho).</td>
    </tr></tbody></table>

### Modificadores de Tamanho
<table class="table table-bordered"><tbody><!-- Results table headers --><tr><th>Tamanho</th>
      <th>Descrição</th>
    </tr><tr><td>(Numero)</td>
      <td>Número minimo de caracteres a serem printados. Se o valor a ser printado for menor que o numero, será adicionado espaços em branco para atigir o numero limite. O valor nao é trucado caso seja maior que o limite.</td>
    </tr><tr><td>*</td>
      <td>O tamanho nao é especificado na formatação da string, mas é passado como argumento precedendo o argumento a ser formatado</td>
    </tr></tbody></table>

### Modificadores de precisão
<table class="table table-bordered"><tbody><!-- Results table headers --><tr><th>.precisão</th>
      <th>Descrição</th>
    </tr><tr><td>.numero</td>
      <td>Para formatos inteiros (i, d, u, o, x, X): precisão especifica o numero minimo de digitos a serem mostrados. Se a quantidade de digitos for menor que o limite, entao serão acrescentados zeros ao final. O valor nao é truncado se a quantidade de digitos for maior que o limite.  Precisão 0 significa que o nenhum valor é printado se o numero for 0.<br><br>Para formatos e, E, f: é o numero de digitos que serão mostrados depois do ponto decimal.<br><br>Para formatos g e G: é o numero maximo de digitos significantes a serem mostrados.<br><br>Para s: é o numero maximo de caracteres a serem mostrados. Por padrão, todos os caracteres serão mostrados até o caracter nulo que finaliza uma string (por exemplo \n)<br><br>Para c: não tem efeito.<br><br>Quando nenhuma precisão é especificada, o padrão é 1. Se o periodo é especificado sem um valor explicito para precisão, 0 é assumido.</td>
    </tr><tr><td>.*</td>
      <td>A precisão nao é especificada na formatação da string, mas é passado como argumento precedendo o argumento a ser formatado.</td>
    </tr></tbody></table>

### Modificadores de quantidade
<table class="table table-bordered"><tbody><!-- Results table headers --><tr><th>quantidade</th>
      <th>Descrição</th>
    </tr><tr><td>h</td>
      <td>O argumento é interpretado como um short int ou unsigned short int (só se aplica aos formatadores de inteiro: i, d, o,  u,  x,  X).</td>
    </tr><tr><td>l</td>
      <td>O argumento é interpretado como um long int ou unsigned long int (só se aplica aos formatadores de inteiro: i, d, o,  u,  x,  X) e como um caractere de largura ou cadeia de caracteres de largura para formatadores c e s.</td>
    </tr><tr><td>L</td>
      <td>O argumento é interpretado como um long double (somente para formatadores de float: e, E, f, g e G).<br></td>
    </tr></tbody></table>

O `printf` é muito poderoso, e espero ter ajudado a conhece-lo melhor.

Obrigado, até a proxima!
