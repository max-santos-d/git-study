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

## Branches

No Git, os branches (ramificações) são caminhos separados de desenvolvimento no seu repositório. Eles permitem que você trabalhe em diferentes recursos ou correções de bugs de forma isolada, sem interferir no código principal do projeto.

Ao criar um novo branch, você está essencialmente criando uma cópia do estado atual do seu código. Você pode fazer alterações nesse branch sem afetar o código em outros branches. Isso é útil para experimentar novas ideias, desenvolver recursos separadamente ou corrigir problemas sem comprometer o código principal.

Para criar um novo branch no Git, você pode usar o comando `git branch` seguido pelo nome do novo branch que você deseja criar. Aqui está como você pode fazer isso:

~~~bash
# Para criar um novo branch chamado "nome-do-branch":
git branch nome-do-branch
~~~

No entanto, apenas criar um branch não muda automaticamente para ele. Para começar a trabalhar no novo branch que você acabou de criar, você precisa usar o comando `git checkout` ou `git switch`, seguido pelo nome do branch:

~~~bash
# Para mudar para o novo branch:
git checkout nome-do-branch
~~~

ou

~~~bash
# Para mudar para o novo branch (a partir do Git 2.23):
git switch nome-do-branch
~~~

Uma maneira mais conveniente de criar e mudar para um novo branch ao mesmo tempo é usar o comando `git checkout -b`, que cria um novo branch e muda para ele em uma única etapa:

~~~bash
# Para criar e mudar para um novo branch:
git checkout -b nome-do-branch
~~~

Após criar e mudar para um novo branch, você pode fazer alterações no seu código e realizar commits normalmente. Essas alterações ficarão isoladas no novo branch até que você decida mesclá-las de volta para o branch principal ou para outro branch.

Para realizar o procedimento de merge entre branches no Git, você segue estes passos:

1. Mude para o branch de destino: Primeiro, mude para o branch onde você deseja mesclar as alterações. Por exemplo, se você deseja mesclar as alterações de um branch chamado `feature`, mude para o branch onde você deseja aplicar essas alterações, geralmente é a branch principal (`master` ou `main`).

    ~~~bash
    git checkout master
    ~~~

2. Execute o merge: Agora, você pode mesclar as alterações do branch `feature` para o branch atual usando o comando `git merge`.

    ~~~bash
    git merge feature
    ~~~

    Isso mesclará as alterações do branch `feature` para o branch atual (neste caso, `master`).

3. Resolva conflitos (se houver): Se houver conflitos entre as alterações nos dois branches (ou seja, se as mesmas partes do código foram alteradas em ambos os branches), o Git informará sobre esses conflitos e você precisará resolvê-los manualmente. O Git marcará os arquivos com conflitos e você precisará editar esses arquivos para resolver as diferenças.
4. Conclua o merge: Após resolver todos os conflitos, adicione os arquivos modificados ao stage (área de preparação) e faça um commit para concluir o merge.

    ~~~bash
    git add .
    git commit -m "Merge branch 'feature' into master"
    ~~~

5. Verifique o histórico: Após o merge, você pode verificar o histórico de commits para confirmar que o merge foi bem-sucedido.

    ~~~bash
    git log
    ~~~

Você pode continuar trabalhando no branch principal ou, se necessário, excluir o branch "feature" após mesclar suas alterações:

~~~bash
git branch -d feature
~~~

## Git Flow

O Git Flow é um modelo de fluxo de trabalho popular para o Git que fornece um conjunto de regras e convenções sobre como organizar branches em um repositório Git. Foi proposto por Vincent Driessen em um artigo em 2010 e se tornou uma prática comum em muitos projetos de software.

O Git Flow define uma estrutura para gerenciar o desenvolvimento de novos recursos, lançamentos e correções de bugs em um projeto. Ele utiliza várias branches para organizar o fluxo de trabalho, incluindo:

1. Branch master: Esta é a branch principal do projeto. Ela sempre reflete o estado de produção do software.
2. Branch develop: Esta é a branch de desenvolvimento principal. Ela é usada para integrar e testar novos recursos antes de serem mesclados na branch master.
3. Branches de feature (recursos): Para cada nova funcionalidade ou recurso que você deseja adicionar ao projeto, você cria uma nova branch de feature a partir da branch develop. Uma vez concluída, essa branch de feature é mesclada de volta para a develop.
4. Branches de release (lançamento): Quando você está se preparando para fazer um novo lançamento do software, você cria uma branch de release a partir da develop. Nesta branch, você pode finalizar os detalhes do lançamento, como correções de bugs e atualizações de documentação. Depois que o lançamento é considerado pronto, ele é mesclado na master e na develop, e uma tag é criada para marcar o lançamento.
5. Branches de hotfix (correção de bugs): Se surgir um bug em produção que precise ser corrigido imediatamente, você pode criar uma branch de hotfix a partir da master. Após a correção do bug, essa branch é mesclada de volta para a master e também para a develop.

O Git Flow fornece uma estrutura organizada e bem definida para colaboração em equipe e gerenciamento de versões em projetos de software. No entanto, é importante notar que o Git Flow pode ser um pouco pesado para projetos pequenos ou equipes menores, e pode haver variações ou simplificações do modelo dependendo das necessidades do projeto. 

- [saiba mais - atlassian](https://www.atlassian.com/br/git/tutorials/comparing-workflows/gitflow-workflow)
- [saiba mais - alura](https://www.alura.com.br/artigos/git-flow-o-que-e-como-quando-utilizar)

![Ramificações](./img/git-flow.svg)

## Implementação do Git Flow

Existem duas formas de implementar o Git Flow, a primeira é utilizar os comandos básicos do Git, a outra é utilizar uma CLI que ajuda a simplificar o fluxo do Git Flow.

1. Inicialize o repositório Git:
    - A primeira coisa que temos que fazer é criar uma Branch Develop a partir da Branch Master. Para isso, utilize:
        - Com comando básico do Git: `git checkout -b develop`
        - Com a CLI do Git-flow: `git flow init`
2. Branch Feature:
    - Criação de uma feature
        - Com comandos básicos do Git:

            ~~~bash
            git checkout develop
            git checkout -b name-feature
            ~~~

        - Com a CLI do Git-flow: `git flow feature start name-feature`
    - Finalização de uma feature:
        - Com comandos básicos do Git:

            ~~~bash
            git checkout develop
            git merge name-feature
            ~~~

        - Com a CLI do Git-flow: `git flow feature finish name-feature`
3. Branch Hotfix:
    - Criação de um Hotfix
        - Com comandos básicos do Git:

            ~~~bash
            git checkout master
            git checkout -b name-hotfix
            ~~~

        - Com a CLI do Git-flow: `git flow hotfix start name-hotfix`
    - Finalização de um Hotfix
        - Com comandos básicos do Git:

        ~~~bash
        git checkout master
        git merge name-hotfix
        git checkout develop
        git merge name-hotfix
        git tag name-hotfix
        ~~~

        - Com a CLI do Git-flow: `git flow hotfix finish name-hotfix`
4. Branch Release:
    - Criação de uma Release
        - Com comandos básicos do Git:

            ~~~bash
            git checkout develop
            git checkout -b release/1.0.0
            ~~~

        - Com a CLI do Git-flow: `git flow release start 1.0.0`
    - Finalização de uma Release
        - Com comandos básicos do Git:

            ~~~bash
            git checkout master
            git merge release/1.0.0
            git checkout develop
            git merge release/1.0.0
            git tag 1.0.0
            ~~~

        - Com a CLI do Git-flow: `git flow release finish 1.0.0`
