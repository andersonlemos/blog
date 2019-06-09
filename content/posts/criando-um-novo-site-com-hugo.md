---
title: "Criando Um Novo Site Com Hugo"
date: 2019-06-09T12:47:26-03:00
author: "Anderson Lemos"
slug: "criando-novo-site-com-hugo"
draft: true
---

# Criando um novo site com Hugo

![HUGO](https://d33wubrfki0l68.cloudfront.net/30790d6888bd8af863fb2b5c33a7f337cdbda243/4e867/images/hugo-logo-wide.svg)




Como prometido na última postagem, volto para mostrar a criação de um projeto básico com Hugo.



A sintaxe para criação de um novo site é:

```
$hugo new site [path] [flags]
```

Onde *path* é o caminho para criação do novo projeto e *flags* são as opções de criação.

```
    --force                   inicializa em um diretório existente
-f, --format string           configura o formato dos arquivos de configuracao usados (padrão "toml")
-h, --help                    ajuda para o site
```

No nosso caso seguiremos o tutorial de introdução do [site do projeto](https://gohugo.io):

```
$hugo new site quickstart	 // Onde quickstart é o nome do projeto a ser criado
```

O próximo passo é adicionar um tema ao projeto criado. Escolha um em [themes.gohugo.io](https://themes.gohugo.io/) e fique atento a versão mínima suportada por cada um.

```
$cd quickstart
$git init
$git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
```
Edite o arquivo config.toml na pasta raiz do projeto *quickstart*  criado e inclua:

```
theme = "ananke"  // Tema instalado e que será usado no projeto
```

Com o tema instalado, vamos agora incluir uma postagem de teste.

```
$hugo new posts/primeira-postagem.md
```

Inicie o servidor HUGO  habilitando a visualização das postagens marcadas como rascunho *Drafts*:

```
$hugo server -D

                   | EN
+------------------+----+
  Pages            | 10
  Paginator pages  |  0
  Non-page files   |  0
  Static files     |  3
  Processed images |  0
  Aliases          |  1
  Sitemaps         |  1
  Cleaned          |  0

Total in 16 ms
Watching for changes in /Documentos/quickstart/{content,data,layouts,static,themes}
Watching for config changes in /Documentos/quickstart/config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

Já sabemos criar um novo site, adicionar um tema e criar novas postagens.Agora é só explorar as demais funcionalidades
disponíveis.

Até a próxima.



 *Referências:*

*HUGO: Quickstart 2019.Disponível em: <https://gohugo.io/getting-started/quick-start/>*

*HUGO Themes: Complete List 2019.Disponível em: <https://themes.gohugo.io/>*