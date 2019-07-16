---
title: Começando com ASP.NET Core.
date: '2019-07-16T10:00:13-03:00'
categories:
  - Net Core
  - Como Instalar
tags:
  - ''
autoThumbnailImage: true
thumbnailImagePosition: top
thumbnailImage: /images/uploads/aspnetcore.png
coverImage: ''
---
# Começando com ASP.NET Core.

![Logotipo do ASP.NET Core](/images/uploads/aspnetcore.png)

## O que é ASP.NET Core ?

O desenvolvimento do ASP.NET Core foi motivado pelo desejo de criar um framework web

com quatro objetivos principais:

* Ser executado e desenvolvido em _cross-platform_.
* Ter uma arquitetura modular facilitando a manutenção.
* Ser _Open Source_.
* Ser aplicável às tendências atuais no desenvolvimento _web_ como  _client-side applications_ e _cloud deploy_.

Para alcançar todos esses objetivos, a _Microsoft_ precisava de uma plataforma que pudesse fornecer

bibliotecas subjacentes para criar objetos básicos, como listas e dicionários, e executar, por exemplo, operações de arquivo simples.

Até este ponto, o desenvolvimento do _ASP.NET_ era focado e dependente do _.NET Framework_ somente em _Windows_. Para _ASP.NET Core_, a _Microsoft_ criou uma plataforma leve que roda no _Windows_, _Linux_ e _macOS_ chamada ._NET Core_ .

O _.NET Core_ compartilha muitas das mesmas APIs do _.NET Framework_, mas é menor e

atualmente implementa apenas um subconjunto dos recursos que o _.NET Framework_ fornece, com o

objetivo de obter um modelo de implementação e programação mais simples. 

Com o _.NET Core_ somente, é possível criar aplicativos de console  _cross-platform_

de modo que a conversão  para um aplicativo da Web envolve  somente a adição de bibliotecas, como mostra a figura abaixo.

![ASP.NET Core Application Model](/images/uploads/net-core-application-model.jpg)

Chega de enrolação e vamos a instalação.

**Pré-Requisitos**:

* [SDK do NET Core 2.2](https://www.microsoft.com/net/download/all) - Disponível em <https://www.microsoft.com/net/download/all>.

Siga as instrulçoes para a plataforma de sua preferência.

Após a instalação vamos a criação de um simples projeto do tipo _Console Application_.

Agora abra o console e digite:

```
dotnet new console -o helloWorldApp
```

Esse comando cria o projeto _helloWorldApp_, na pasta desejada.

Por fim, execute o projeto criado com:

```
dotnet run
```

A saída do console deve ser parecida com:

![Saída do comando dotnet run da aplicação console apresenta a string "Hello World!" como saída.](/images/uploads/saidaterminal.jpg)

Ficou muito mais fácil criar aplicativos  para múltiplas plataformas com essa nova tecnologia da _Microsoft. _

_Referências_ :

_ASP.NET: ASP.NET Free. Cross-platform. Open source.Disponível em: [https://dotnet.microsoft.com/apps/aspnet](https://dotnet.microsoft.com/apps/aspnet)_

_ASP.NET Core In Action, Andrew Lock_: Disponível em: [https://www.manning.com/books/asp-net-core-in-action](https://www.manning.com/books/asp-net-core-in-action)_
