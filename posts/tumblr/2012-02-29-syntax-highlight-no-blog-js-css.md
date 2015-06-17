---
layout: post
title: ! '[dica rapida] syntax hightlight no seu blog com javascript'
tags:
- syntax highlight
- programming
- developer
- blog
- trick
---
se voce tem um blog sobre programação, provavelmente voce postará snippets de codigo e provavelmente voce vai querer que esse snippet tenha syntax highlight como no seu editor de codigo preferido.

mas como faz?

é bem facil, basta voce usar um modulo JS e CSS chamado google code prettify.

para cofigura-lo na pagina. basta voce colocar esses 2 links no seu html.

<link href="prettify.css" type="text/css" rel="stylesheet" />
<script type="text/javascript" src="prettify.js"></script>


e depois chamar uma função no load da pagina.

$(function() {prettyPrint();});



  obs: para chama-lo assim voce deve carregar o jquery na pagina.
  
  obs 2: mais informaçoes de configuração, veja o readme. do projeto.


e agora?

basta voce colocar seu codigo dentro de uma tag code ou pre com a classe prettyprint e pronto, seu codigo vai ficar bonito na pagina!

um exemplo:

<code class="prettyprint">print "Hello World!</code>


é isso, até mais!
