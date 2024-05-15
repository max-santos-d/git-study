# Git

## Sobre

O Git é um sistema de controle de versão distribuído, o que significa que cada usuário tem uma cópia completa do repositório de código em seu próprio computador. Ele foi criado por Linus Torvalds em 2005, o mesmo criador do kernel do Linux, para ajudar no desenvolvimento do Linux.

A necessidade surgiu quando os desenvolvedores do kernel Linux não estavam satisfeitos com as opções de controle de versão disponíveis na época. O principal problema era que outros sistemas de controle de versão centralizados não conseguiram lidar bem com o volume e a complexidade do desenvolvimento do kernel do Linux, que envolvia uma grande quantidade de ramificações e contribuições de desenvolvedores em todo o mundo.

Assim, Linus Torvalds desenvolveu o Git como uma solução distribuída e eficiente para esses desafios específicos. Ele permite que os desenvolvedores trabalhem de forma independente em suas próprias cópias locais do repositório, enquanto ainda podem colaborar e sincronizar suas alterações com outros desenvolvedores de forma eficiente. Desde então, o Git se tornou o sistema de controle de versão padrão para uma ampla variedade de projetos de software, devido à sua robustez, velocidade e flexibilidade.

Na prática, o Git funciona seguindo alguns conceitos-chave:

1. Repositório: O Git gerencia um repositório, que é basicamente um diretório onde seus arquivos e histórico de alterações são armazenados.
2. Snapshot: Em vez de armazenar apenas as alterações feitas em cada arquivo, o Git armazena instantâneos (snapshots) de todo o sistema de arquivos em determinados pontos no tempo. Isso significa que ele captura o estado completo do projeto a cada commit. 
3. Commits: Um commit é uma alteração no seu projeto. Cada commit no Git é como uma foto do seu código em um determinado momento. Cada commit tem um hash único que o identifica.
4. Branches (ramificações): O Git permite que você crie ramificações do seu código. Isso é útil para desenvolver novos recursos ou corrigir bugs sem afetar o código principal. As ramificações no Git são leves e rápidas de criar.
5. Merging (fundir): Depois de trabalhar em uma ramificação e estar satisfeito com as alterações, você pode fundir (merge) essa ramificação de volta à ramificação principal (geralmente a master ou main).
6. Remoto: Além do seu repositório local, você pode ter um repositório remoto, como no GitHub, GitLab ou Bitbucket. Isso permite colaboração e compartilhamento de código com outras pessoas.

O fluxo de trabalho típico com o Git envolve:

- Clonar um repositório: Criar uma cópia local de um repositório remoto.
- Fazer alterações nos arquivos.
- Adicionar as alterações ao índice (staging area).
- Confirmar (commit) as alterações no repositório local.
- Enviar (push) as alterações para um repositório remoto.
- Atualizar (pull) seu repositório local com as alterações de um repositório remoto.
- Gerenciar ramificações para desenvolvimento de recursos separados.
- Fundir (merge) ramificações quando as alterações estiverem prontas.

## Instalação

Para instalar o Git no Windows e no Linux, siga estas instruções:

No Windows:

1. Baixe o instalador do Git para Windows no site oficial: [Git for Windows](https://gitforwindows.org/).
2. Execute o instalador baixado e siga as instruções do assistente de instalação.
3. Durante a instalação, você pode optar por usar as configurações padrão ou personalizá-las de acordo com suas preferências.
4. Após a conclusão da instalação, abra o prompt de comando (cmd) e verifique se o Git foi instalado corretamente executando o comando `git --version`.

No Linux:

1. A maioria das distribuições Linux já vem com o Git pré-instalado. No entanto, se não estiver instalado ou se você quiser garantir que tenha a versão mais recente, você pode instalar usando o gerenciador de pacotes da sua distribuição.
    - Para sistemas baseados em Debian (como Ubuntu, Debian), você pode usar o apt:

    ~~~bash
    sudo apt update
    sudo apt install git
    ~~~

    - Para sistemas baseados em Red Hat (como Fedora, CentOS), você pode usar o dnf ou yum:

    ~~~bash
    sudo dnf install git   
    # (ou)
    sudo yum install git
    ~~~

    - Para sistemas baseados em Arch Linux, use o pacman:

    ~~~bash
    sudo pacman -Sy git
    ~~~

    - Para outras distribuições, consulte a documentação específica da distribuição.

2. Após a instalação, você pode verificar se o Git foi instalado corretamente executando o comando `git --version` no terminal. 




