## Objetivo Desse Repositório:

O objetivo deste repositório é orientar desenvolvedores na instalação e configuração do WSL2 no Windows, permitindo que o Docker seja executado de forma nativa. Ao seguir este guia, você será capaz de criar um ambiente de desenvolvimento integrado e otimizado, utilizando o poder do Docker sem a complexidade de máquinas virtuais tradicionais. Além disso, o repositório inclui instruções para rodar um contêiner com SQL Server no Docker, possibilitando um setup completo para desenvolvimento de aplicações que utilizam bancos de dados. Este passo a passo busca simplificar todo o processo, tornando-o acessível para desenvolvedores de todos os níveis.


## Benefícios de Usar WSL2 com Docker Nativo

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

> **É essencial manter o Windows atualizado, pois o WSL 2 depende de uma versão atualizada do Hyper-V. Verifique o Windows Update.**
>
> 
