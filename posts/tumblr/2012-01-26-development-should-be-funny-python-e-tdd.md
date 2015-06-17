---
layout: post
title: development |should| be_funny - Python e TDD
tags:
- python
- should-dsl
- tdd
---

Should o que?!
O should-dsl é uma ferramenta de teste que tem como principal objetivo tornar o codigo mais legivel e limpo. (http://www.should-dsl.info/)
Ok, mas #comofas?
Depois de instalado (o site ensina como fazer) é bem simples começar a escrever os testes. Tá duvidando, então olha só:
Esse exemplo eh a implementacao das specs da musica Só para Loucos – Ventania
So Para Loucos Spec Spec



class Pessoa:
		louco = False
		careta = True

		def colher_cogumelos(self):
		    self.cogumelos = [''cogumelo1'', ''cogumelo2'', ''cogumelo3'', ''cogumelo4'', ''cogumelo5'']
		    return self.cogumelos

		def fazer_cha(self, *ingredientes):
		    cha = ingredientes
		    return cha

		def beber(self, oque):
		    self.louco = True
		    self.careta = False
		    self.versos = [''espinho'', ''espinho'']

		    return self

		def guardar_cogumelos(self, cogumelos):
		    self.recanto_espiritual = cogumelos
		    return self.recanto_espiritual


	class TestSoParaLoucos(unittest.TestCase):
	    def setUp(self):
	    	self.pessoa = Pessoa()

	    def test_deve_ser_careta_sem_tomar_nada(self):
	    	self.pessoa |should| be_careta

	    def test_deve_estar_louco_depois_de_tomar_um_cha_de_cogumelo(self):
	    	cogumelos = self.pessoa.colher_cogumelos()

	    	cha_de_cogumelo = self.pessoa.fazer_cha(cogumelos)
	    	cha_de_cogumelo |should| contain(cogumelos)

	    	self.pessoa.beber(cha_de_cogumelo) |should| be_louco
	    	self.pessoa.versos |should| have(2).espinhos

	    def test_deve_guardar_cogumelos_escondidos(self):
	        cogumelos = self.pessoa.colher_cogumelos()
	    	self.pessoa.guardar_cogumelos(cogumelos)
	    	self.pessoa.recanto_espiritual |should| have(5).cogumelos

	if __name__ == ''__main__'':
	    unittest.main()




Só isso?
Isso foi só um exemplo ludico, pra mostrar as possibilidades da ferramneta! Hoje ela contem varios matchers(as funções de teste) para os mais variados objetivos. Voce pode ver a lista completa aqui
Voce tambem pode fazer seus proprios matchers
Acabou?
Se voce gostou do projeto e quer ajudar, aqui vc encontra varias formas de contribuir!
Entao eh isso, Até a proxima xD
