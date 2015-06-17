---
layout: post
title: Vagrant - Maquinas virtuais leves e rapidas
tags:
- continuous integration
- desenvolvimento web
- maquina virtual
- ruby
- vagrant
---

Se voce é programador e precisa subir maquinas virtuais pra testar sites no IE 6/7/8/9, ou quer fazer deploy para ambientes iguais os de produção, e pra mais varias coisas que precisam ser rapidas e são mega chatas e demoradas, e voce usa VirtualBox – Voce esta fazendo isso errado.
Ok, entao eu uso o que?
O vagrant é uma ferramenta para a construção e distribuição de ambientes dedesenvolvimento virtualizados, escrita em ruby que usa o VirtualBox da Oracle como base, e prove funcionalidades que permitem criar, distribuir, reproduzir e configurar Maquinas Virtuais(VM) de forma rapida (fonte: github do projeto).
ComoFas
Como eu disse anterior mente é muito facil, basta ter o ruby, e a virtualbox instalada, uma internet boa ajuda tambem.
Tendo isso instalado vamos começar:
Execute esse comando:


$ gem install vagrant


Certifique-se que tudo está instalado corretamente.
Antes de criar sua maquina, crie uma pasta para abrigar os arquivos de configuraçao:


$ mkdir vagrant-machine


Agora vamos criar uma VM com ubuntu 10.04


$ cd vagrant-machine $ vagrant box add lucid32 http://files.vagrantup.com/lucid32.box $ vagrant init lucid32 $ vagrant up


Feito isso sua VM ja está pronta para ser acessada!
Mas é só isso mesmo?!
Claro que nao!!! Agora vamos configurar seu ambiente! Primeiro, abra o arquivo Vagrantfile na pasta vagrant-machine e deixe ele assim:


Vagrant::Config.run do |config| # Setup the box config.vm.box = "lucid32" end


Execute o comando de reload para carregar suas modificações


$ vagrant reload


Teste o acesso a sua VM para ver se está funcionando corretamente


$ vagrant ssh


OBS: Tudo que voce colocar na pasta onde está seu Vagrantfile, aparecerá na VM na pasta /vagrant. Para ter certeza, execute este comando na VM:


$ ls /vagrant


Agora acabou?
Bom agora voce tem que instalar os pacotes que voce precisa no seu ambiente. Para isso eu escolhi usar o chef para gerenciar a instalação. Esse processo depende muito do seu ambiente, entao deixarei referencias para montagem de ambientes usando o chef.
Para estudar o vagrant e o chef eu fiz uma VM configurada para ser um servidor de CI
Nela estao instalados os seguintes pacotes: * Django 1.3 * Apache * git * MySql * Jenkins (servidor de CI)
Download aqui
OBS: Execute a VM e acesse o servidor de CI pela url http://localhost:8080/
Referencias:
Tutorial em ingles
Using vagrant as a Team
Video Tutorial
Making CI easier to do than not to with Hudson CI and Vagrant
Chef Docs
Using vagrant for you web development
Bom, é isso, divirtam-se com suas novas VMs rapidas e praticas.
Duvidas e criticas, deixem nos comentarios.
Até a proxima
