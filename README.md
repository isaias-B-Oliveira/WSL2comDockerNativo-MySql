## Objetivo Desse Repositório:

O objetivo deste repositório é orientar desenvolvedores na instalação e configuração do WSL2 no Windows, permitindo que o Docker seja executado de forma nativa. Ao seguir este guia, você será capaz de criar um ambiente de desenvolvimento integrado e otimizado, utilizando o poder do Docker sem a complexidade de máquinas virtuais tradicionais. Além disso, o repositório inclui instruções para rodar um contêiner com SQL Server no Docker, possibilitando um setup completo para desenvolvimento de aplicações que utilizam bancos de dados. Este passo a passo busca simplificar todo o processo, tornando-o acessível para desenvolvedores de todos os níveis.

## O que e o WSL2 ?

O **WSL2** (Windows Subsystem for Linux 2) é a segunda versão do subsistema da Microsoft que permite rodar um kernel Linux completo diretamente no Windows. Ele foi criado para melhorar a integração entre o Windows e Linux, permitindo que desenvolvedores usem ferramentas e utilitários nativos do Linux sem a necessidade de rodar uma máquina virtual completa.

### Características do WSL2:

- **Kernel Linux Real**: Diferente da primeira versão (WSL1), que traduzia chamadas do sistema Linux para o Windows, o WSL2 roda um kernel Linux completo em uma máquina leve.
- **Desempenho**: O WSL2 oferece melhor performance, especialmente em operações de I/O, como leitura e escrita de arquivos.
- **Suporte a Docker**: Ele permite a execução do Docker nativamente no Windows, eliminando a necessidade de uma máquina virtual dedicada para rodar contêineres.
- **Integração com Windows**: Permite que você acesse o sistema de arquivos do Windows a partir do Linux e vice-versa, facilitando o fluxo de trabalho entre os dois sistemas.
- **Ideal para desenvolvedores**: Que precisam de um ambiente Linux sem sair do Windows.



## ✅ Benefícios de Usar WSL2 com Docker Nativo

### 1. Desempenho Melhorado
O WSL2 permite que o Docker rode diretamente no Windows, utilizando o kernel do Linux. Isso resulta em um desempenho significativamente melhorado em comparação com a execução em máquinas virtuais tradicionais.

### 2. Integração com o Windows
Com o WSL2, é possível usar comandos Linux diretamente no terminal do Windows, facilitando a integração entre o sistema de arquivos do Windows e o ambiente de desenvolvimento Linux. Isso torna o fluxo de trabalho mais fluido e eficiente.

### 3. Consumo de Recursos Reduzido
Rodar o Docker nativamente com WSL2 reduz a necessidade de recursos extras, como memória e CPU, que seriam necessários para executar uma máquina virtual completa. Isso libera mais recursos para outras tarefas importantes.

### 4. Configuração Simplificada
O processo de configuração do Docker com WSL2 é mais simples e direto, eliminando a necessidade de configurar uma máquina virtual separada. Isso torna o setup mais acessível, mesmo para aqueles que não têm experiência anterior com virtualização.

### 5. Acesso Direto às Ferramentas de Desenvolvimento
Com o Docker rodando nativamente no WSL2, você tem acesso direto às ferramentas de desenvolvimento Linux, permitindo um ambiente de desenvolvimento mais poderoso e versátil no seu sistema Windows.

### 6. Atualizações e Manutenção Facéis
Manter o WSL2 e o Docker atualizados é simples, com suporte contínuo da Microsoft e da comunidade Docker, garantindo que você tenha acesso às últimas funcionalidades e correções de segurança.

## Requisitos mínimos

* **Windows 10 Home ou Professional**
  - Versão 2004 ou superior (Build 19041 ou superior).
  - Versões mais antigas requerem a instalação manual do WSL 2. Ver tutorial [https://learn.microsoft.com/en-us/windows/wsl/install-manual](https://learn.microsoft.com/en-us/windows/wsl/install-manual).

* **Windows 11 Home ou Professional**
  - Versão 22000 ou superior (qualquer Windows 11).

* Uma máquina compatível com virtualização (verifique a disponibilidade de acordo com a marca do seu processador. Se sua máquina for mais antiga pode ser necessária habilita-la na BIOS).

* Pelo menos 4GB de memória RAM (Recomendado 8GB).

Provavelmente seu Windows já está na versão suportada, mas verifique isto acessando `Todas as Configurações > Sistema > Sobre`. Caso não esteja, use o Assistente do Windows Update para atualizar a sua versão do Windows.

## 1️⃣ 1° Passo para Instalação do WSL 2

Todas as instruções abaixo são para o Windows 10/11.

### Windows Update

Verifique se seu Windows está atualizado, pois o WSL 2 depende de uma versão atualizada do Hyper-V. Verifique o Windows Update.

### Atualizar o WSL

Com a versão 2004 do Windows 10 ou Windows 11, o WSL já estará presente em sua máquina, execute o comando para pegar a versão mais recente do WSL:

``` bash
wsl --update
```

### 2️⃣ 2° Passo: Atribuir a versão default do WSL para a versão 2

A versão 2 normalmente é a default, mas a versão 1 do WSL pode estar como default, execute o comando abaixo para definir como default a versão 2:

``` bash
wsl --set-default-version 2
```

### Instale o Ubuntu

Execute o comando:

```bash
wsl --install
```

Este comando irá instalar o `Ubuntu` como o Linux padrão. 

Se você quiser instalar uma versão diferente do Ubuntu, execute o comando `wsl -l -o`. Será listado todas as versões de Linux disponíveis. Instale a versão escolhida com o comando `wsl --install -d nome-da-distribuicao`.

Sugiro o Ubuntu (sem versão) por ser uma distribuição popular e que já vem com várias ferramentas úteis para desenvolvimento instaladas por padrão. mais vc pode trabalhar com quantas Distro LINUX vc quiser.

Após o término do comando, você deverá criar um **nome de usuário** que poderá ser o mesmo da sua máquina (crie um nome de usuário sem espaço e caracteres especiais) e uma **senha** (defina uma senha forte). **Guarde Esta senha**, Ela será usada para instalar pacotes e realizar operações de superusuário.

`Agora se vc for no seu explorador de arquivo vai aparecer a Distribuição que vc instalou.`

<img src="/img/explorado.png">

---
Para abrir uma nova janela do Ubuntu, basta digitar `Ubuntu` no menu iniciar e clicar no ícone do Ubuntu.

<img src="/img/ubumto.png">

---
Recomendo o uso do [Windows Terminal](https://docs.microsoft.com/pt-br/windows/terminal/get-started) como terminal padrão para desenvolvimento no Windows. Ele agregará o shell do Ubuntu, assim como o PowerShell e o CMD em uma única janela, além de permitir personalização de cores e temas. Se aparecel esse terminal Parabéns, seu WSL2 já está funcionando!

<img src="/img/WindowsTerminal.png">
 
---

### Integre o Wsl2 com VSCode.

O Visual Studio Code tem uma extensão chamada **Remote - WSL** que permite acessar o WSL 2 diretamente do VSCode. Com esta extensão, você pode editar seus arquivos diretamente no WSL 2, rodar comandos, instalar extensões e muito mais.

Veja mais sobre esta extensão em [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl).

<img src="/img/vscodeestencao.png">

---

Ao abrir um projeto que está dentro do Linux, é importante que o modo WSL do VSCode esteja ativado. No canto inferior esquerdo do VSCode, clique no botão `><` e selecione `Connect to WSL`.

<img height="150px" width="320px" src="/img/remoteconecte.png">     <img height="150px" width="320px" src="/img/wslconecte.png">

Isto irá conectar o VSCode ao WSL 2 e então poderá abrir o projeto que está dentro do Linux. Você verá que o botão `><` mudará para `WSL: Ubuntu`.

<img height="150px" width="320px" src="/img/wslubunto.png">

---

### Beneficios da integração Wsl2 com Vscode.
 - **Desempenho Nativo do Linux:** Mesmo que você esteja usando o VS Code no Windows, você tem o desempenho nativo do Linux para compilar, executar e debugar.
 - **Ambiente de Desenvolvimento Completo:** Ferramentas e extensões que exigem um ambiente Linux funcionam sem a necessidade de uma máquina virtual separada.
 - **Integração Perfeita:** O VS Code permite que você edite e debuge como se estivesse no Linux, mas sem sair da interface familiar do Windows.
   
Em resumo, ao usar o VS Code com WSL2, você pode aproveitar tanto as ferramentas nativas do Linux quanto a interface gráfica e as funcionalidades poderosas do VS Code, tornando o processo de desenvolvimento mais fluido e eficiente.   
