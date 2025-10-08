# Git Add

Por padrão, quando você cria um novo arquivo dentro do seu projeto Git, ele não está sendo rastreado pelo Git. Então, para informar ao git que ele deve começar a rastrear o arquivo, você precisa usar o comando `git add`.

A sintaxe é a seguinte:

```bash
git add NOME_DO_ARQUIVO
```

No nosso caso, temos apenas 1 arquivo dentro do nosso projeto chamado `README.md`, então para adicionar esse arquivo ao Git, podemos usar o seguinte comando:

```bash
git add README.md
```

Se você executar `git status` novamente, verá uma saída diferente:

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

Aqui você verá que agora há algumas alterações preparadas e prontas para serem commitadas. Além disso, o Git informa que o `README.md` é um novo arquivo que acabou de ser preparado e não foi rastreado antes.

Caso você tenha vários arquivos, pode listá-los todos separados por espaço após o comando `git add` para prepará-los todos de uma vez, em vez de executar `git add` várias vezes para cada arquivo individual:

```bash
git add arquivo1.html arquivo2.html arquivo3.html
```

Com o comando acima, adicionamos os 3 arquivos executando `git add` apenas uma vez, porém em alguns casos, você pode ter muitos arquivos novos, e adicioná-los um por um pode ser muito demorado.

Então existe uma forma de preparar absolutamente todos os arquivos do seu projeto atual, especificando um ponto após o comando `git add` assim:

```bash
git add .
```

> Nota: Você precisa ter cuidado com isso, pois em alguns casos pode haver arquivos que você não deseja adicionar ao Git.

Com isso, estamos prontos para avançar e aprender sobre o comando `git commit`.
