## Objetivo Desse Repositório:

O objetivo deste repositório é orientar desenvolvedores na instalação e configuração do WSL2 no Windows, permitindo que o Docker seja executado de forma nativa. Ao seguir este guia, você será capaz de criar um ambiente de desenvolvimento integrado e otimizado, utilizando o poder do Docker sem a complexidade de máquinas virtuais tradicionais. Além disso, o repositório inclui instruções para rodar um contêiner com SQL Server no Docker, possibilitando um setup completo para desenvolvimento de aplicações que utilizam bancos de dados. Este passo a passo busca simplificar todo o processo, tornando-o acessível para desenvolvedores de todos os níveis.

## ❓ O que e o WSL2 ?

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

### 3️⃣ 3° Passo: Instale o Ubuntu

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

## ⚙️ Integre o Wsl2 com VSCode.

O Visual Studio Code tem uma extensão chamada **Remote - WSL** que permite acessar o WSL 2 diretamente do VSCode. Com esta extensão, você pode editar seus arquivos diretamente no WSL 2, rodar comandos, instalar extensões e muito mais.

Veja mais sobre esta extensão em [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl).

<img src="/img/vscodeestencao.png">

---

Ao abrir um projeto que está dentro do Linux, é importante que o modo WSL do VSCode esteja ativado. No canto inferior esquerdo do VSCode, clique no botão `><` e selecione `Connect to WSL`.

<img height="150px" width="320px" src="/img/remoteconecte.png">     <img height="150px" width="320px" src="/img/wslconecte.png">

Isto irá conectar o VSCode ao WSL 2 e então poderá abrir o projeto que está dentro do Linux. Você verá que o botão `><` mudará para `WSL: Ubuntu`.

<img height="150px" width="320px" src="/img/wslubunto.png">

---

## ✅ Beneficios da integração Wsl2 com Vscode.
 - **Desempenho Nativo do Linux:** Mesmo que você esteja usando o VS Code no Windows, você tem o desempenho nativo do Linux para compilar, executar e debugar.
 - **Ambiente de Desenvolvimento Completo:** Ferramentas e extensões que exigem um ambiente Linux funcionam sem a necessidade de uma máquina virtual separada.
 - **Integração Perfeita:** O VS Code permite que você edite e debuge como se estivesse no Linux, mas sem sair da interface familiar do Windows.
   
Em resumo, ao usar o VS Code com WSL2, você pode aproveitar tanto as ferramentas nativas do Linux quanto a interface gráfica e as funcionalidades poderosas do VS Code, tornando o processo de desenvolvimento mais fluido e eficiente.   

## ❓ O que e o Docker ?

O Docker é uma plataforma de código aberto que permite a criação, o gerenciamento e a execução de contêineres de software. Contêineres são pacotes que contêm uma aplicação e todas as suas dependências (bibliotecas, ferramentas de sistema, etc.), garantindo que a aplicação possa ser executada de forma consistente em diferentes ambientes, como desenvolvimento, teste e produção.

## Componentes Principais do Docker:
**Contêineres:**
 - Um contêiner é uma instância isolada de um aplicativo que contém tudo o que ele precisa para funcionar, como código, bibliotecas e variáveis de ambiente.
Ao contrário das máquinas virtuais, os contêineres compartilham o kernel do sistema operacional e são mais leves, rápidos de iniciar e eficientes em termos de recursos.

**Imagens Docker:**
 - Uma imagem Docker é um "modelo" ou blueprint para criar contêineres. Ela contém o código da aplicação e tudo que ela precisa para rodar, como dependências, sistema de arquivos e configurações.
Imagens são imutáveis, ou seja, uma vez criadas, não podem ser alteradas. Isso garante consistência na execução de contêineres.

**Docker Engine:**
 - O Docker Engine é o mecanismo que gerencia a execução dos contêineres. Ele permite que você crie, execute e gerencie contêineres em seu sistema.
   
**Docker Hub:**
 - O Docker Hub é um repositório público (ou privado) onde você pode encontrar e compartilhar imagens Docker. Ele facilita o download e a distribuição de contêineres.
   
**Docker Compose:**
 - O Docker Compose é uma ferramenta usada para definir e executar múltiplos contêineres Docker. Ele permite que você configure ambientes de contêineres complexos com apenas um arquivo YAML.

## Como o Docker Funciona:
O Docker utiliza uma tecnologia de contêinerização que envolve:

- Isolamento de Processos: Cada contêiner roda em um processo separado e não interfere nos outros contêineres ou no sistema principal.
- Portabilidade: Como tudo que a aplicação precisa está dentro do contêiner, você pode rodá-la em qualquer ambiente que suporte Docker, como no seu computador, no servidor de produção ou na nuvem.
- Eficiência: Como os contêineres compartilham o kernel do sistema operacional, eles são mais leves e rápidos em comparação com máquinas virtuais, que têm um sistema operacional completo dentro delas.
- Reprodutibilidade: Usando imagens imutáveis, você garante que o ambiente de desenvolvimento, teste e produção seja exatamente o mesmo.
- Escalabilidade: Docker facilita o uso de várias instâncias de contêineres, permitindo a escalabilidade de aplicações.

Casos de Uso:

- Desenvolvimento de Software: Desenvolvedores usam Docker para criar ambientes de desenvolvimento consistentes e rápidos.
- Deploy de Aplicações: Equipes de operações usam Docker para fazer deploy de aplicações em contêineres, garantindo que funcionem da mesma maneira em diferentes servidores.
- Microservices: Docker é amplamente usado para criar arquiteturas de microserviços, onde diferentes partes de uma aplicação são separadas em contêineres individuais.

Por exemplo, se você desenvolver uma aplicação em Node.js com várias dependências, você pode "empacotá-la" em um contêiner Docker. O contêiner garantirá que, em qualquer lugar onde você rodar a aplicação (em outro computador ou servidor), ela funcionará exatamente da mesma maneira. Em resumo, o Docker é uma ferramenta poderosa que facilita o desenvolvimento, distribuição e execução de aplicativos em ambientes isolados e portáteis, otimizando o uso de recursos e garantindo consistência entre diferentes ambientes de execução.

## ⚙️ Agora vamos Instalar o Docker com Docker Engine (Docker Nativo).

A instalação do Docker no WSL 2 é idêntica a instalação do Docker em sua própria distribuição Linux, portanto se você tem o Ubuntu é igual ao Ubuntu, se é Fedora é igual ao Fedora. A documentação de instalação do Docker no Linux por distribuição está [aqui](https://docs.docker.com/engine/install/), mas vamos ver como instalar no Ubuntu.


> ⚠️ **Quem está migrando de Docker Desktop para Docker Engine, temos duas opções**
> 1. Desinstalar o Docker Desktop.
> 2. Desativar o Docker Desktop Service nos serviços do Windows. Esta opção permite que você utilize o Docker Desktop, se necessário, para a maioria dos usuários a desinstalação do Docker Desktop é a mais recomendada.
>Se você escolheu a 2º opção, precisará excluir o arquivo ~/.docker/config.json e realizar a autenticação com Docker novamente através do comando "docker login"
>
> ⚠️ **Se necessitar integrar o Docker com outras IDEs que não sejam o VSCode**
>
> 
> É necessário habilitar a conexão ao servidor do Docker via TCP. Vamos aos passos:
> 1. Crie o arquivo /etc/docker/daemon.json: `sudo echo '{"hosts": ["tcp://0.0.0.0:2375", "unix:///var/run/docker.sock"]}' > /etc/docker/daemon.json`
> 2. Reinicie o Docker: `sudo service docker restart`
> 
> Após este procedimento, vá na sua IDE e para conectar ao Docker escolha a opção TCP Socket e coloque a URL `http://IP-DO-WSL:2375`. Seu IP do WSL pode ser encontrado com o comando `cat /etc/resolv.conf`.
> 
> Se caso não funcionar, reinicie o WSL com o comando `wsl --shutdown` e inicie o serviço do Docker novamente.
>
> 
> ⚠️ O VSCode já se integra com o Docker no WSL desta forma através da extensão Remote WSL ou Remote Container. entao não e nessesrio realisar as configuraçõens acima.
>

## 1️⃣ Execute os comandos no terminal do Ubunto:

```
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
**Entendendo esses Comandos:**
- Esses comandos configuram o sistema para instalar o Docker diretamente do repositório oficial do Docker, garantem a autenticidade dos pacotes usando chaves GPG e instalam o Docker Engine junto com suas ferramentas associadas. Após a execução desses comandos, o Docker estará pronto para uso no seu sistema Ubuntu rodando no WSL2 ou em uma instalação nativa do Ubuntu.

## 2️⃣ Adicione o repositório do Docker na lista de sources do Ubuntu:

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

> OBSERVAÇÃO: Se você estiver usando uma distribuição diferente do Ubuntu, veja os comandos de instalação no documentação do Docker [https://docs.docker.com/engine/install/](https://docs.docker.com/engine/install/)

**Entendendo esses Comandos:**
- Esses comandos configuram o sistema para permitir a instalação do Docker diretamente do repositório oficial do Docker para Ubuntu, garantindo que os pacotes sejam autenticados com segurança usando a chave GPG. Em seguida, você poderá instalar o Docker Engine e suas ferramentas usando os comandos `apt-get` sem precisar adicionar manualmente o repositório ou chave a cada instalação.

## 3️⃣ Dê permissão para rodar o Docker com seu usuário corrente:

```
sudo usermod -aG docker $USER
```

## 4️⃣ Reiniciar o WSL via linha de comando do Windows para que não seja necessário autorização root para rodar o comando docker:

```
wsl --shutdown
```


## 5️⃣ Acessar novamente o Terminal do Ubuntu e iniciar o serviço do Docker:
Esse e o Comando para iniciar o Docker manualmente:
Atenção o comando `sudo service docker start` exigirá a senha do usuário que está executando o comando, (Aquela que vc criou quando instalou o Ubunto).
```
sudo service docker start
```
Este comando acima terá que ser executado toda vez que o Linux for reiniciado. Se caso o serviço do Docker não estiver executando, mostrará esta mensagem de erro ao rodar comando `docker`:

## ⚠️ Erro ao iniciar o Docker no Ubuntu 22.04

> Se mesmo ao iniciar o serviço do Docker acontecer o seguinte erro ou similar retornando essa mensagem:
> 
> - `Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?`
>
> Rode o comando `sudo update-alternatives --config iptables` e escolha a opção 1 `iptables-legacy`
>
> Rode novamente o `sudo service docker start`. Rode algum comando Docker como `docker ps` para verificar se está funcionando corretamente. Se não mostrar o erro acima, está ok.

<!--linha 575-->
  
