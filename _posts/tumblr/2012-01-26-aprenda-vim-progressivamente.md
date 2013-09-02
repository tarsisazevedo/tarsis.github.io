---
layout: post
title: Aprenda Vim Progressivamente
tags:
- howto
- programacao
- programador
- tutorial
- vim
---

Sou usuario do vim a algum tempo e sempre estou procurando aprender mais e mais sobre esse excelente editor.
Recentemente encontrei um otimo post no blog do Yann Esposito para iniciantes aprenderem vim rapidamente e tambem para veteranos querendo aprender algumas magicas desse otimo edito de texto.
Gostei tanto do post que resolvi traduzi-lo para divulgar o vim e mostrar como voar com ele.
Então vamos ao post!


TL;DR: Quer aprender vim (o melhor editor conhecido pela humanidade) da forma mais rapida possivel. Eu sugiro um caminho. Comece aprendendo o basico pra sobreviver, entao integre todos os truques devagar

Vim, o editor de texto de seis bilhões de dólares

Melhor, mais rapido, mais forte

Aprenda vim e ele será seu ultimo editor de texto. Ele não é o melhor editor de texto, eu sei. É dificil de aprender, mas incrivel de usar.
 
Eu sugiro aprende-lo em 4 passos:
Sobreviva
Sinta-se confortavel
Sinta-se melhor, mais rapido, mais forte
Use os superpoderes do vim
No final dessa jornada você se tornará um superstar do vim!
Mas antes de começar, um aviso. Aprender vim será doloroso no começo. Isso leva tempo. É muito parecido com aprender a tocar um instrumento musical. Não espere ser eficiente com vim do que com outro editor em 3 dias. Na verdade vai levar 2 semanas ao inves de 3 dias.
Nivel 1 - Sobreviva
insta-le o vim
abra o vim
NÃO FAÇA NADA! Leia
Em um editor de texto normal, escrever no teclado é o suficiente para escrever alguma coisa e ve-la na tela. Não dessa vez. Vim está no modo Normal. Vamos entrar no modo de Inserção. Digite a letra i.
Agora voce se sente um pouco melhor. Voce pode digitar textos como um editor de texto normal. Para voltar para o modo normal, tecle ESC.
Voce sabe trocar entre o modo Normal e de Inserção. E agora a lista de comandos que voce pode usar no modo Normal para sobreviver:

i - modo de Inserção. Tecle ESC para voltar ao modo Normal.
x - para deletar o caracter em baixo do cursor.
:wq - Salvar e Sair (:w para salvar, :q para sair).
dd - deletar e copiar a linha atual.
p - colar.
Recomendado:
hjkl (altamente recomendado, mas nao obrigatorio) - movimentos basicos do cursor (←↓↑→). Dica: j é a seta para baixo.
:help <comando> - mostra o help do <comando>, voce pode começar a usar o :help sem nada mais.

Somenten 5 comandos. Isso é muito pouco para começar. Uma vez que esses comandos começarem a sair naturalmente (pode ser no final do dia), voce pode ir para o nivel 2.
Mas antes apenas uma observação no modo Normal. Em editores normais, para copiar voce deve usar a tecla Ctrl (Ctrl + c geralmente). Na verdade, quando voce pressiona o Ctrl, é como se todas as funcionalidades das teclas mudassem. Com vim no modo Normal, é como se seu Ctrl sempre estivesse pressionado.
Uma ultima observação sobre notações:
ao invés de escrever Ctrl-V, vamos escrever <C-V>
comandos começam com : e terminam com <enter>. Por exemplo, quando eu escrever :q isso significa :q<enter>
Nivel 2 - Sinta-se confortavel
Voce sabe os comandos para sobreviver. Agora é hora de aprender mais alguns comandos. Eu sugiro:
Variações do modo de Inserção:

a - insere depois do cursor
o - insere uma nova linha depois da linha corrente
O - insere uma nova linha antes da linha corrente
cw - substitui do cursor até o final da palavra

Movimentos Basicos:

0 - vai para o inicio da linha
^ - vai para o primeiro caracter nao-branco da linha
$ - vai para o final da linha
g_ - vai para o ultimo caracater nao-branco da linha
/padrao - procura por padrao

Copiar/Colar

P - cola antes do cursor, relembre que p é para colar depois da posição corrente.
yy - copia a linha corrente, mais facil que o ddP

Desfazer/Refazer:

u - desfazer
<C-r> (**Ctrl-r**) - refazer

Carregar/Salvar/Sair/Mudar Arquivo (buffer):

:e <caminho/para/arquivo> - abrir
:w - salvar
:saveas <caminho/para/arquivo> - salvar em <caminho/para/arquivo/>
:x, ZZ ou :wq - salvar e sair (:x somente salva se necessario)
:q! - sair sem salvar, tambem :qa! até mesmo se houver algum buffer modificado escondido
:bn (resp. :bp) - mostra o proximo (resp. anterior) arquivo (buffer)

Separe algum tempo para aprender esses comandos. Uma vez aprendido, voce deve estar apto para fazer tudo que voce faz em qualquer outro editor. Mas até agora, isso é um pouco estranho. Mas siga-me até o proximo nivel e voce verá porque.
Nivel 3 - Melhor. Mais Forte. Mais Rapido.
Parabens por chegar tao longe! Nós podemos começar a parte interessante. No nivel 3, nós iremos falar somente sobre comandos que são compativeis com o vi antigo.
Melhor
Vamos ver como o vim faz para te ajudar a repetir um comando:
. (ponto) - irá repetir o ultimo comando
N<comando> - irá repetir o comando N vezes.
Alguns exemplos, abre um arquivo e digite:

2dd - irá deletar 2 linhas
3p - irá colar o texto 3 vezes
100idesu ESC - irá escrever “desu” 100 vezes
. (ponto) - irá repetir o ultimo comando, escrevendo mais 100 vezes “desu”
3. - irá escrever 3 “desu” (e não 300, muito inteligente)

Mais forte
Saber como se mover de modo eficiente no vim é muito importante. Não pule esta seção.
NG - vai para a linha N
gg - atalho para 1G, vai para o começo do arquivo
G - vai para a ultima linha
Andando em palavras:

w - vai para o começo da palavra seguinte
e - vai para o final da palavra seguinte
Por padrao, uma palavra é composta de letras e caracteres underscore ( _ ). Vamos chamar de uma PALAVRA um grupo de letras separadas por caracteres em branco. Se voce quiser considerar PALAVRA, entao use letras maiusculas:
W - vai para o inicio da PALAVRA seguinte
E - vai para o final da PALAVRA seguinte 





Agora vamos falar sobre movimentos mais eficientes:

% - Vai para o correspondente (, [, {
* (resp #) - vai para a proxima (resp anterior) ocorrencia da palavra sob o cursor.

Acredite em mim, esses tres comandos são ouro.
Mais rapido
Lembra sobre a importancia dos movimentos no vim? Aqui está a razão. Muitos comandos podem ser usados seguindo um formato geral:

<posição de inicio><comando><posição final>

Por exemplo: 0y$ significa:
0 - vai para o começo dessa linha
y - copie daqui
$ - até o final desta linha
Nós tambem podemos fazer coisas como ye, copie daqui até o final da palavra. Tambem podemos fazer y2/foo copie até a segunda ocorrencia de “foo”.
Mas se foi possivel com y (copiar), é tambem possivel com d (deletar), v (seleção visual), gU (maiuscula), gu (minuscula), etc…
Nivel 4 - Super poderes com vim
Com todos os comandos anteriores voce ja deve se sentir confortavel com o vim. Mas agora, aqui estao as features realmente maneiras. Algumas dessas features foram a razão pra eu começar a usar o vim.
mover-se na linha corrente: 0, ^, $, g_, f, F, t, T, ,(virgula), ;

0 - Vai para a coluna 0
^ - Vai para o primeiro caracter da linha
$ - vai para a ultima coluna
g_ - Vai para o ultimo caracter da linha
fa - Vai para a proxima ocorrencia da letra a na linha. , (resp ;) irá para a ocorrencia anterior da busca (resp proxima).
t, - Vai para o caracter anterior a primeira ocorrencia de ,
3fa - Vai procurar a terceira ocorrencia da letra a
F e T - Parecido com f e t, porem procura pra tras




Uma dica muito util é :dt" que irá remover tudo antes de ".
Seleção por zona <ação>a<objeto> ou <ação>i<objeto>
Esses comandos só podem ser usados depois de uma operação no modo Visual. Mas eles são muito poderosos.
<ação>a<objeto> ou <ação>i<objeto>
Onde ação pode ser qualquer ação, por exemplo, d (delete), y (copiar), v (selecionar no modo Visual). E um objeto pode ser: w uma palavra, Wuma PALAVRA(palavra extendida), s uma sentença e p um paragrafo. Mas tambem pode ser um caracter natural como ", '', ), }, ].
Digamos que o cursor esteja no primeiro o de (map (+) ("foo")).

vi" - irá selecionar foo.
va" - irá selecionar "foo".
vi) - irá selecionar "foo".
va) - irá selecionar ("foo").
v2i) - irá selecionar map (+) ("foo").
v2a) - irá selecionar (map (+) ("foo")).

Selecionas blocos retangulares <C-v>.
Blocos retangularss são muito uteis para comentar muitas linhas de código. Tipicamente: ^<C-v><C-d>I-- [ESC]

^ - vai para o inicio da linha
<C-v> - inicia a seleção por blocos
<C-d> - move para baixo (como jjj or %, etc… )
I-- [ESC] - escreve — para comentar cada linha


Note que no Windows voce poderá ter que usar <C-q> ao inves de <C-v> se seu clipboard nao estiver vazio.
Completar: <C-n> e <C-p>.
No modo de Inserção, digite no inicio de uma palavra, e entao digite <C-p>, magicamente…

Macros: qa faça alguma coisa q, @a, @@
qa vai gravar suas açoes num registrador a. Entao @a irá refazer a macro salva no registrador a como se voce tivesse feito isso na mão. @@ é um atalho para refazer a ultima macro executada.

Exemplo
Numa linha que contem o numero 1, digite isso:
qaYp<C-a>q  
qa - começa a gravar
Yp - duplica esta linha
<C-a> - incrementa um numero
q - para a gravaçao

@a - escreverá 2 abaixo do 1
@@ - escreverá 3 abaixo do 2
Agora faça 100@@ e criará uma lista de numeros até 103.


Seleção Visual: v, V, <C-v>
Vimos um exemplo com <C-v>. Há tambem v e V. Uma vez que a seleçao foi feita, voce pode:

J - juntar todas as linhas.
< (resp. >) - indentar para a esquerda (resp. para a direita).
= - auto indentação


Adicione alguma coisa no fim das linhas selecionadas:

<C-v>
vá para a linha desejada (jjj ou <C-d> ou /padrao ou % etc…)
$ vá para o fina da linha
A, escreva alguma coisa, [ESC]


Splits: :split e :vsplit.
Aqui estao os comandos principais, mas voce pode olhar mais em :help split.

:split - irá criar um split (:vsplit criará um split vertical).
<C-w><dir> - onde dir é qualquer um de hjkl para mudar de split.
<C-w>_ (resp. <C-w>|) - maximiza o tamanho do split (resp. split vertical).
<C-w>+ (resp. <C-w>-) - Aumenta (resp. diminui) o split.




Conclusao
Aqui estao 90% dos comandos que eu uso todos os dias. Eu sugiro que voce aprenda nao mais que 1 ou 2 comandos por dia. Depois de duas ou tres semanas voce começará a sentir o poder do vim nas suas mãos.
Aprender Vim é mais uma questao de treinamento que de memorização. Felizmente vim vem com otimas ferramentas e uma execelente documentação. Rodevimtutor para voce se familiarizar com os comandos basicos. Alem disso voce deve ler atentamente está pagina: :help usr_02.txt.
Entao, voce aprenderá sobre !, folds, registradores, os plugins e muitas outras features. Aprender vim é como se estivesse aprendendo piano e tudo ficará bem.
Fim do post
Agora que voce ja sabe vim, use-o da maneira correta. Esqueça seu mouse, Ctrl-c + Ctrl+v, use as features do vim, se forçe a usa-las, eu garanto que depois que voce se sentir confortavel, vai voar.
Qualquer duvida e/ou critica podem deixar nos comentarios.
Até a proxima
OBS: Post totalmente editado no VIM, usando markdown.
