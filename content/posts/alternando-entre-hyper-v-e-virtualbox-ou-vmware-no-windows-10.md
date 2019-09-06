---
title: Alternando entre Hyper-V e VirtualBox ou VMware no Windows 10
date: '2019-09-06T09:37:25-03:00'
categories:
  - Virtualizaçã
tags:
  - Virtualização
  - VirtualBox
  - Hyper-V
keywords:
  - Virtualização
  - VirtualBox
  - Hyper-V
  - ''
autoThumbnailImage: false
thumbnailImagePosition: top
coverImage: /images/uploads/virtualbox.jpg
---
Esses dias estive com um problema para resolver no trabalho. Comecei alguns estudos de Flutter para desenvolvimento de _apps_ e precisei instalar o _VirtualBox_. Foi aí que descobri que ele (_VirtualBox_) não funciona em sistemas Windows com o _Hyper-V_ ativo.  E agora? O que fazer?

Depois de algumas horas pesquisando encontrei os motivos. 

De acordo com o site da _Microsoft _: 

> "_A virtualização cria um ambiente de computação simulado ou virtual em vez de um ambiente físico. A virtualização costuma incluir versões de hardware, sistemas operacionais, dispositivos de armazenamento e outros, todas geradas por computador. Isso permite que as organizações particionem um único computador físico ou servidor em diversas máquinas virtuais. Cada máquina virtual pode interagir de forma independente e executar diferentes sistemas operacionais ou aplicativos ao mesmo tempo em que todas compartilham os recursos de um único computador host."_

![Antes: 3 servidores diferentes para 3 sistemas operacionais e serviços. Depois: Somente um servidor é necessário para os 3 servidores anteriores e sistemas operacionais.](/images/uploads/virtualization.jpg)

Em resumo, a virtualização é a troca da mentalidade física para a lógica.

Seguindo esse conceito, existem 2 tipos de _Hypervisors_:

![Tipos de Hypervisors](/images/uploads/typesofhypervisors.jpg)

Os _Hypervisors tipo 1_, os chamados _bare-metal_, interagem diretamente com o hardware do computador, sendo independentes do host.

Os _Hypervisors  tipo 2_, são dependentes do host e dos serviços de virtualização, fornecidos pelo sistema operacional. 

Somente um tipo de _Hypervisor_ pode ter o controle das instruções _VT-x_ do processador, por vez e por isso não é possível o uso do _VirtualBox_ com o _Hyper-V_ ativo.

Essas solução permitirá o uso do _Hyper-V_ e _VMWare_ ou _VirtualBox_ na mesma máquina, mas não simultaneamente.  Será necessário reiniciar o computador enquanto alterna  entre os virtualizadores.

## Passo-a-Passo

Usaremos o **_bcdedit.exe_** para criar uma nova entrada de boot com o _Hyper-V_ desativado.

**Passo 1:** Abra o prompt de comando como administrador. **(Use o CMD pois esses comandos não funcionam no Powershell)**

**Passo 2**: Execute o seguinte comando: 

```
C:\>bcdedit /copy {current} /d “Hyper-V Desabilitado”
```

Você pode usar aqui sua própria descrição ao invés de ** "Hyper-V desabilitado"**. 

Logo após a execução verá a seguinte saída na tela:

```
The entry was successfully copied to {<sua GUID aparecerá aqui>}.
```

**Passo 3:**  Logo após, execute o comando a seguir:

```
C:\>bcdedit /set {<GUID mostrada no passo 2>} hypervisorlaunchtype off
```

Você verá a mensagem:

```
The operation completed successfully.
```

**Passo 4: ** Reinicie o computador enquanto segura a tecla _Shift_. Aparecerá uma tela com a opção de inicialização para **_"Use another operation system"_**.  Selecione a nova entrada **_"Hyper-V Desabilitado"_** e aguarde a inicialização do Windows com o _Hyper-V_ desabilitado e o _VirtualBox_ funcionando.

![Escolher outro sistema operacional.](/images/uploads/use-another-operating-system.jpg)
