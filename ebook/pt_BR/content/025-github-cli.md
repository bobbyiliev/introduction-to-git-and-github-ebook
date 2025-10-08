# GitHub CLI

A GitHub CLI ou `gh` é basicamente o GitHub na linha de comando.

Você pode interagir com sua conta do GitHub diretamente pelo terminal e gerenciar coisas como pull requests, issues e outras ações do GitHub.

Neste tutorial, vou dar uma visão rápida de como instalar o `gh` e como usá-lo!

## Instalação do GitHub CLI

Como estou usando Ubuntu, para instalar o `gh` você precisa rodar os seguintes comandos:

```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key C99B11DEB97541F0
sudo apt-add-repository https://cli.github.com/packages
sudo apt update
sudo apt install gh
```

Se você estiver no Mac, pode instalar o `gh` usando o Homebrew:

```bash
brew install gh
```

Para outros sistemas operacionais, recomendo seguir os passos da documentação oficial [aqui](https://github.com/cli/cli#installation).

Depois de instalar o `gh`, você pode verificar se está funcionando com o comando:

```bash
gh --version
```

Isso mostrará a versão do `gh`:

```
gh version 1.0.0 (2020-09-16)
https://github.com/cli/cli/releases/tag/v1.0.0
```

No meu caso, estou usando a versão mais recente `gh` v1.0.0, lançada há poucos dias.

## Autenticação

Depois de instalar o `gh`, você precisa fazer login na sua conta do GitHub.

Para isso, execute o comando:

```bash
gh auth login
```

Você verá a seguinte saída:

```
? What account do you want to log into?  [Use arrows to move, type to filter]
> GitHub.com
  GitHub Enterprise Server
```

Você pode escolher entre GitHub.com ou GitHub Enterprise. Pressione enter e siga o processo de autenticação.

Outro comando útil é o `gh help`. Ele mostra uma lista dos comandos disponíveis do `gh` que você pode usar:

```
USAGE
  gh <command> <subcommand> [flags]

CORE COMMANDS
  gist:       Criar gists
  issue:      Gerenciar issues
  pr:         Gerenciar pull requests
  release:    Gerenciar releases do GitHub
  repo:       Criar, clonar, fazer fork e visualizar repositórios

ADDITIONAL COMMANDS
  alias:      Criar atalhos de comando
  api:        Fazer uma requisição autenticada à API do GitHub
  auth:       Login, logout e atualizar autenticação
  completion: Gerar scripts de autocompletar para o shell
  config:     Gerenciar configuração do gh
  help:       Ajuda sobre qualquer comando

FLAGS
  --help      Mostrar ajuda do comando
  --version   Mostrar versão do gh

EXEMPLOS
  $ gh issue create
  $ gh repo clone cli/cli
  $ gh pr checkout 321

VARIÁVEIS DE AMBIENTE
  Veja 'gh help environment' para a lista de variáveis de ambiente suportadas.

SAIBA MAIS
  Use 'gh <command> <subcommand> --help' para mais informações sobre um comando.
  Leia o manual em https://cli.github.com/manual

FEEDBACK
  Abra uma issue usando 'gh issue create -R cli/cli'
```

Agora vamos clonar um projeto existente para testar. Como exemplo, podemos usar o repositório [LaraSail](https://github.com/thedevdojo/larasail). Em vez de usar o comando padrão `git clone`, vamos usar o `gh`:

```bash
gh repo clone thedevdojo/larasail
```

Você verá a seguinte saída:

```
Cloning into 'larasail'...
```

Depois disso, entre na pasta:

```bash
cd larasail
```

Agora estamos prontos para usar alguns dos comandos mais úteis do `gh`!

## Comandos úteis do GitHub CLI

Usando o `gh`, você pode obter praticamente todas as informações do seu repositório no GitHub sem sair do terminal.

Aqui estão alguns comandos úteis:

### Trabalhando com issues do GitHub

Para listar todas as issues abertas, execute:

```bash
gh issue list
```

A saída será:

```
Showing 4 of 4 open issues in thedevdojo/larasail

#25  Add option to automatically create database                                                  (enhancement)  about 3 months ago
#22  Remove PHP mcrypt as it is no longer needed                                                                 about 3 months ago
#11  Add redis support                                                                                           about 8 months ago
#10  Wondering about the security of storing root MySQL password in /etc/.larasail/tmp/mysqlpass                 about 3 months ago
```

Você pode criar uma nova issue com o comando:

```bash
gh issue create --label bug
```

Ou visualizar uma issue existente:

```bash
gh issue view '#25'
```

Isso retorna todas as informações da issue específica:

```
Add option to automatically create a database
Open • bobbyiliev opened about 3 months ago • 0 comments

Labels: enhancement

  Add an option to automatically create a new database, a database user and
  possibly update the database details in the .env file for a specific project

View this issue on GitHub: https://github.com/thedevdojo/larasail/issues/25
```

### Trabalhando com seu repositório GitHub

Você pode usar o comando `gh repo` para criar, clonar ou visualizar um repositório existente:

```bash
gh repo create
gh repo clone cli/cli
gh repo view --web
```

Por exemplo, ao rodar `gh repo view`, você verá as informações do README do seu repositório diretamente no terminal.

### Trabalhando com Pull Requests

Você pode usar o comando `gh pr` com vários argumentos para gerenciar seus pull requests.

Algumas opções disponíveis são:

```
  checkout:   Fazer checkout de um pull request no git
  checks:     Mostrar status de CI para um pull request
  close:      Fechar um pull request
  create:     Criar um pull request
  diff:       Ver alterações em um pull request
  list:       Listar e filtrar pull requests neste repositório
  merge:      Mesclar um pull request
  ready:      Marcar um pull request como pronto para revisão
  reopen:     Reabrir um pull request
  review:     Adicionar uma revisão a um pull request
  status:     Mostrar status dos pull requests relevantes
  view:       Visualizar um pull request
```

Com esses comandos, você está pronto para executar as principais ações do GitHub diretamente no terminal!

### Conclusão

Agora você sabe o que é a ferramenta GitHub CLI e como usá-la! Para mais informações, recomendo conferir a documentação oficial:

[https://cli.github.com/manual/](https://cli.github.com/manual/)

Sou fã de ferramentas de linha de comando! Elas podem facilitar sua vida e automatizar muitas tarefas repetitivas do dia a dia!

Publicado originalmente aqui:
[O que é GitHub CLI e como começar](https://devdojo.com/bobbyiliev/what-is-github-cli-and-how-to-get-started)
