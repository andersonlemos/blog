---
title: Instalando e configurando HUGO
date: 2019-06-06T14:14:39.000Z
categories:
  - hugo
  - linux
  - go
  - Como instalar
autoThumbnailImage: false
---
## Quem é esse tal de HUGO?

![Logo HUGO](https://d33wubrfki0l68.cloudfront.net/30790d6888bd8af863fb2b5c33a7f337cdbda243/4e867/images/hugo-logo-wide.svg)

De acordo com o site oficial (https://gohugo.io) do projeto:

> _"Hugo é um dos mais populares geradores de sites estáticos de código aberto. Com sua incrível velocidade e flexibilidade, Hugo torna a construção de sites mais divertidos novamente."_

Alguns dos seus benefícios são:

* Tempo de construção _(build)_ extremamente baixo (<1 ms por página).
* Multiplataforma.
* Suporte nativo a _Markdown_ - (https://www.markdownguide.org/basic-syntax/).
* Suporte integrado ao _Google Analytics_.

Pré requisitos de instalação:

* Git - Disponível em https://git-scm.com.
* Go - Disponível em https://golang.org (pelo menos a versão 1.11).

Começarei com a instalação de Go, já que utilizo Linux Mint 18 - Sarah (https://linuxmint.com) e já veio com Git instalado por padrão.

## Instalando GO no Linux Mint.

Abra o terminal e atualize seu sistema.

```
sudo apt-get update -y 
```

Agora, baixe os binários para sua versão no site oficial (https://golang.org/dl/).

```
wget https://dl.google.com/go/go1.12.5.linux-amd64.tar.gz 
```

Descompacte o arquivo baixado e instale no local de sua preferência. No meu caso escolhi o diretório _/usr/local_ .

```
tar -xvf go1.12.5.linux-amd64.tar.g
mv go /usr/local
```

Adicione _/usr/local/go/bin_ à variável de ambiente **PATH**. 

```
export PATH=$PATH:/usr/local/go/bin
```

E por fim teste se está tudo certo com a instalação

```
go version
```

A saída do comando deve ser algo parecido com:

```
go version go1.12.5 linux/amd64
```

Agora sim daremos prosseguimento a instalação do _HUGO_.

Clonaremos o repósitorio do projeto no _Github_ com a última versão dos pacotes.

```
mkdir $HOME/src
cd $HOME/src
git clone https://github.com/gohugoio/hugo.git
cd hugo
go install --tags extended
```

Remova `--tags extended` se você não precisa do suporte a _Sass/SCSS_.

Verifique a instalação digitando:

```
hugo version
```

A saída do comando deve ser algo parecido com:

```
Hugo Static Site Generator v0.55.5-A83256B9 linux/amd64 BuildDate: 2019-05-	02T13:04:07Z 
```

Tarefa finalizada!

Por hoje é só. Da próxima vez mostro como criar um projeto básico. 



_Referências:_

_The Go Programming Language: Install the Go tools, 2019. Página inicial.
Disponível em: <https://golang.org/doc/install>_ .

_HUGO: Install Hugo, 2019. Página inicial.Disponível em: <https://gohugo.io/getting-started/installing/>_ .

_TechAdmin_._net:How to Install Go on Linuxmint, 2019. Página inicial.
Disponível em: <https://tecadmin.net/install-go-on-linuxmint/>_ .
