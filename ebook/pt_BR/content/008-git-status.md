# Git Status

Sempre que você fizer alterações no seu projeto Git, é importante verificar o que mudou antes de fazer um commit ou antes de enviar suas alterações para o GitHub, por exemplo.

Para checar o status atual do seu projeto, você pode usar o comando `git status`. Se você executar o comando `git status` no mesmo diretório onde inicializou seu projeto Git no capítulo anterior, verá a seguinte saída:

```
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

Como este é um repositório novo, ainda não há commits nem alterações. Então, vamos criar um arquivo `README.md` com algum conteúdo genérico. Podemos executar o seguinte comando para isso:

```bash
echo "# Projeto Demo" >> README.md
```

Esse comando irá escrever `# Projeto Demo` e armazenar no arquivo `README.md`.

Se você rodar `git status` novamente, verá a seguinte saída:

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
nothing added to commit but untracked files present (use "git add" to track)
```

Como você pode ver, o Git está detectando que há 1 novo arquivo que não está sendo rastreado no momento, chamado `README.md`, que acabamos de criar. E o Git já está sugerindo que usemos o comando `git add` para começar a rastrear o arquivo. Vamos aprender mais sobre o comando `git add` no próximo capítulo!

Vamos usar bastante o comando `git status` nos próximos capítulos! Ele é especialmente útil quando você modificou vários arquivos e quer verificar o status atual e ver todos os arquivos modificados, atualizados ou excluídos.
