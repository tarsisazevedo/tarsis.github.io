---
layout: post
title: Testes em Javascript - Jasmine
tags:
- jasmine
- programming
- javascript
- tdd
- bdd
---
Testes automatizados emergiram como uma das boas praticas da engenharia de software, e seus resultados sao comprovadamente eficazes.

Eu utilizo bastante essas tecnicas quando programo em python/django com ferramentas como o splinter, unittest entre outras. Porem quando programava em javacript, eu sempre senti falta desses testes automatizados.

E o Jasmine?


  tl;dr - Jasmine is a behavior-driven development framework for testing your JavaScript code.
  It does not depend on any other JavaScript frameworks.
  It does not require a DOM.
  And it has a clean, obvious syntax so that you can easily write tests.


Em setembro do ano passado (2011), comecei a trabalhar no projeto de cobertura de eventos na globo.com. E tinhamos como desafio principal, atualizar uma pagina em tempo real via streaming com fotos, videos e textos. Pra isso os componentes da pagina teriam que interagir muito, recebendo e tratando os dados enviados do streaming. Usamos muito js com o framework mootools, e pra testar usamos o jasmine, o que nos proporcionou uma segurança e qualidade de codigo excelentes!

Agora chega de falar!

Show me the code

Pra começar, vc descreve um cenario que vai testar.

Como exemplo, vamos fazer um fizzbuzz

{% highlight javascript %}
describe("Fizz Buzz", function(){
    expect(fizzbuzz(3)).toEqual("fizz");
});
{% endhighlight %}


Depois de escrever o teste, a gente escreve um codigo pra passar:

{% highlight javascript %}
var fizzbuzz = function(numero) {
}
{% endhighlight %}


Agora mais um cenario:

{% highlight javascript %}
it("numero igual a cinco, deve retornar buzz",function() {
});
{% endhighlight %}

mais um pouco de codigo:

{% highlight javascript %}
var fizzbuzz = function(numero) {
    return "fizz";
}
{% endhighlight %}


Bom ai vcs podem continuar a brincar e terminar o codigo.

E pra rodar?

Bom vc pode carregar os scripts(download aqui) do jasmine numa pagina html estatica e por ultimo carregar o seu teste.
Um exemplo:

{% highlight html %}
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
  "http://www.w3.org/TR/html4/loose.dtd">
<html>
    <title>Jasmine Test Runner</title>
    <link rel="stylesheet" type="text/css" href="lib/jasmine-1.0.2/jasmine.css">
    <script type="text/javascript" src="lib/jasmine-1.1.0/jasmine.js"></script>
    <script type="text/javascript" src="arquivo/de/teste.js"></script>
</head>
<body>
    <script type="text/javascript">
        jasmine.getEnv().addReporter(new jasmine.TrivialReporter());
        jasmine.getEnv().execute();
    </script>
</html>
{% endhighlight %}


Se vc tem um projeto em ruby com rails, vc pode usar uma gem pra rodar os testes.

Se vc tem um projeto em python, pode usar o jasmine-test-runner, feito pelo cobrateam.

Se vc tem um projeto em outra linguagem, veja aqui como rodar o jasmine.

Entao é isso!

Até a proxima, []’s
