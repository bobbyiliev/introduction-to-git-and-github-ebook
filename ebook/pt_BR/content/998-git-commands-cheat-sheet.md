# Guia Rápido de Comandos Git

Aqui está uma lista dos comandos Git mencionados ao longo do eBook

* Configuração do Git

Antes de inicializar um novo repositório git ou começar a fazer commits, você deve configurar sua identidade no git.

Para alterar o nome associado aos seus commits, use o comando `git config`:

```bash
git config --global user.name "Seu Nome"
```

O mesmo vale para alterar seu endereço de e-mail associado aos commits:

```bash
git config --global user.email "seuemail@exemplo.com"
```

Assim, quando você fizer um commit e depois verificar o log do git, verá que o commit está associado aos detalhes que você configurou acima.

```bash
git log
```

No meu caso, a saída é assim:

```
commit 45f96b8c2ef143011f11b5f6cc7a3ae20db5349d (HEAD -> main, origin/master, origin/HEAD)
Author: Bobby Iliev <bobby@bobbyiliev.com>
Date:   Fri Jun 19 17:03:53 2020 +0300

    Nginx server name for www version (#26)
```

### Inicializando um projeto

Para inicializar um novo projeto git local, abra seu terminal git ou bash, use `cd` para ir até o diretório onde deseja armazenar seu projeto e então execute:

```bash
git init .
```

Se você já tem um projeto existente no GitHub, por exemplo, pode cloná-lo usando o comando git clone:

```bash
git clone url_do_seu_projeto
```

### Status atual

Para verificar o status atual do seu repositório git local, use o seguinte comando:

```bash
git status
```

Esse é provavelmente um dos comandos mais usados, pois você precisa verificar o status do seu repositório local com frequência para saber quais arquivos foram alterados, preparados ou excluídos.

### Adicionar um arquivo à área de staging

Suponha que você tem um projeto HTML estático e já inicializou seu repositório git.

Depois, em algum momento, decide adicionar um novo arquivo HTML chamado `about-me.html`, já com algum código HTML. Para adicionar esse novo arquivo para que ele seja rastreado pelo git, primeiro use o comando `git add`:

```bash
git add nome_do_arquivo
```

Isso irá preparar seu novo arquivo, o que significa que na próxima vez que você fizer um commit, a alteração fará parte do commit.

Para verificar, você pode rodar novamente o comando `git status`:

```bash
git status
```

Você verá a seguinte saída:

```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   about-me.html
```

### Remover arquivos

Para remover um arquivo do seu projeto git, use o seguinte comando:

```bash
git rm algum_arquivo.txt
```

Depois disso, se rodar `git status` novamente, verá que o arquivo `algum_arquivo.txt` foi excluído:

```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        deleted:    algum_arquivo.txt
``` 

### Descartar alterações de um arquivo

Caso tenha cometido um erro e queira descartar as alterações de um arquivo específico e restaurar o conteúdo desse arquivo como estava no último commit, use o comando abaixo:

```bash
git checkout -- nome_do_arquivo
```

Esse comando é conveniente para reverter rapidamente um arquivo ao seu conteúdo original.

### Commit local

Depois de fazer suas alterações e prepará-las com o comando `git add`, você precisa fazer o commit das alterações.

Para isso, use o comando `git commit`:

```bash
git commit
```

Isso abrirá um editor de texto onde você pode digitar sua mensagem de commit.

Ou, você pode usar a flag `-m` para especificar a mensagem de commit diretamente no comando:

```bash
git commit -m "Mensagem legal de commit aqui"
```

### Listar branches

Para listar todos os branches locais disponíveis, basta rodar o seguinte comando:

```bash
git branch -a
```

Você verá uma lista de branches locais e remotos, a saída será assim:

```
  bugfix/nginx-www-server-name
  develop
* main
  remotes/origin/HEAD -> origin/master
  remotes/origin/bugfix/nginx-www-server-name
  remotes/origin/develop
  remotes/origin/main
```

A palavra `remotes` indica que esses branches são remotos.

### Buscar alterações do remoto e mesclar o branch atual com o upstream

Se você está trabalhando com uma equipe de desenvolvedores no mesmo projeto, muitas vezes precisará buscar as alterações que seus colegas fizeram para tê-las localmente no seu PC.

Para isso, basta usar o comando `git pull`:

```bash
git pull origin nome_do_branch
```

Note que isso também irá mesclar as novas alterações ao branch atual em que você está.

### Criar um novo branch

Para criar um novo branch, basta usar o comando `git branch`:

```bash
git branch nome_do_branch
```

Em vez disso, prefiro usar o comando abaixo, pois ele cria um novo branch e também muda para o branch recém-criado:

```bash
git checkout -b nome_do_branch
```

Se o `nome_do_branch` já existir, você receberá um aviso de que o branch existe e não será mudado para ele.

### Enviar alterações locais para o remoto

Por fim, depois de fazer todas as suas alterações, prepará-las com o comando `git add .` e fazer o commit com o comando `git commit`, você precisa enviar essas alterações para o repositório git remoto.

Para isso, use o comando `git push`:

```bash
git push origin nome_do_branch
```

### Excluir um branch

```bash
git branch -d nome_do_branch
```

### Mudar para um novo branch

```bash
git checkout nome_do_branch
```

Como mencionado acima, se você adicionar a flag `-b`, o branch será criado se não existir.

### Conclusão

Conhecendo os comandos acima, você poderá gerenciar seu projeto como um profissional!

Se quiser melhorar suas habilidades no terminal em geral, recomendo este [curso básico de linha de comando Linux](https://devdojo.com/course/linux-command-line-basics)!
