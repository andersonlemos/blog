---
title: "Instalando e configurando HUGO"
date: 2019-05-31T16:29:31-03:00
author: "Anderson Lemos"
slug: "instalando-e-configurando-hugo"
draft: true
---

## Quem é esse tal de HUGO?

![HUGO](https://d33wubrfki0l68.cloudfront.net/30790d6888bd8af863fb2b5c33a7f337cdbda243/4e867/images/hugo-logo-wide.svg)

De acordo com o [site oficial](https://gohugo.io) do projeto:

> *"Hugo é um dos mais populares geradores de sites estáticos de código aberto. Com sua incrível velocidade e flexibilidade, Hugo torna a construção de sites mais divertidos novamente."*

Alguns dos seus benefícios são:

* Tempo de construção *(build)* extremamente baixo (<1 ms por página)
* Multiplataforma
* Suporte nativo a [*Markdown*](https://www.markdownguide.org/basic-syntax/)
* Suporte integrado ao *Google Analytics*

Pré requisitos de instalação:

* [Git](https://git-scm.com)
* [Go](https://golang.org) (pelo menos a versão 1.11)

Começarei com a instalação de Go, já que utilizo [Linux Mint 18 - Sarah](https://linuxmint.com) e já veio com Git instalado por padrão.

## Instalando GO no Linux Mint

Atualize seu sistema

````
$sudo apt-get update -y
````

Baixe os binários para sua versão no [site oficial](https://golang.org/dl/)

````
$wget https://dl.google.com/go/go1.12.5.linux-amd64.tar.gz
````

Descompacte o arquivo baixado e instale no local de sua preferência. No meu caso escolhi o diretório */usr/local* .

````
$tar -xvf go1.12.5.linux-amd64.tar.g
$mv go /usr/local
````

Adicione */usr/local/go/bin* à variável de ambiente **PATH**. 

````
$export PATH=$PATH:/usr/local/go/bin
````

E por fim teste se está tudo certo com a instalação


````
$go version
go version go1.12.5 linux/amd64
````

Agora sim daremos prosseguimento a instalação do *HUGO*.

Clonaremos o repósitorio do projeto no *Github* com a última versão dos pacotes.

```
mkdir $HOME/src
cd $HOME/src
git clone https://github.com/gohugoio/hugo.git
cd hugo
go install --tags extended
```

Remova `--tags extended` se você não precisa do suporte a *Sass/SCSS*.

Verifique a instalação

```
$hugo version
Hugo Static Site Generator v0.55.5-A83256B9 linux/amd64 BuildDate: 2019-05-	02T13:04:07Z
```

Tarefa finalizada!

Por hoje é só. Da próxima vez mostro como criar um projeto básico. 



*Referências:*

*The Go Programming Language: Install the Go tools, 2019. Página inicial.
Disponível em: <https://golang.org/doc/install>*

*HUGO: Install Hugo, 2019. Página inicial.Disponível em: <https://gohugo.io/getting-started/installing/>*
