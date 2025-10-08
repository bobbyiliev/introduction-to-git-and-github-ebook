# Git Commit

Depois de adicionar/preparar seus arquivos, o próximo passo é realmente fazer o commit das alterações. Então, se você executar `git status` novamente, verá que o Git informa que há alterações para serem commitadas:

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

Neste caso, é apenas o arquivo `README.md` que será commitado. Para isso, podemos executar o seguinte comando:

```bash
git commit -m "Sua mensagem de commit aqui"
```

Explicação do comando:

* `git commit`: aqui, estamos dizendo ao git que queremos fazer o commit das alterações que preparamos com o comando `git add`
* `-m`: esta flag indica que vamos especificar nossa mensagem de commit diretamente após ela
* Por fim, entre aspas está nossa mensagem de commit, é importante escrever mensagens curtas e descritivas

No nosso caso, podemos definir nossa mensagem de commit como `"Commit inicial"` ou `"Adicionar README.md"`, por exemplo.

Se você não especificar a flag `-m`, o Git abrirá o editor de texto padrão que configuramos no capítulo 5, onde você poderá digitar a mensagem de commit diretamente.

Commitando diretamente sem preparar arquivos:

Se você ainda não preparou suas alterações usando o comando `git add`, pode ainda assim fazer o commit de todas as suas alterações diretamente usando o seguinte comando:
```
git commit -a -m "Sua mensagem de commit aqui"
```
A flag `-a` irá automaticamente preparar todas as alterações e fazer o commit delas.

## Assinando Commits
O Git permite que você assine seus commits. Commits assinados com uma assinatura verificada no GitHub e GitLab exibem um selo de verificado como mostrado abaixo.
![Commits assinados no GitHub](https://imgur.com/OvY20rM.png)
![Commit assinado no GitLab](https://i.imgur.com/u5Oait2.png)

Para assinar commits, primeiro você precisa:
* Certificar-se de que tem o GNU GPG instalado em sua máquina.
* Gerar um par de chaves GPG para assinatura, se ainda não tiver:
  ```bash 
  gpg --full-generate-key
  ```
* Use o comando `gpg --list-secret-keys --keyid-format=long` para listar a forma longa das chaves GPG
```bash
gpg --list-secret-keys --keyid-format=long
/Users/bobby/.gnupg/pubring.kbx
---------------------------------
sec   rsa4096/E630A0A00CAA7AAA 2021-10-01 [SC] [expires: 2026-10-01]
      5F1F417F8A043C8888888888E630F6D35CFA7ECD
uid                 [ultimate] Bobby Illiev (For signing git commits) <bobby@bobbyiliev.com>
ssb   rsa4096/46EE4AA180001AA6 2021-10-01 [E] [expires: 2026-10-01]
```
* Copie o ID longo da chave GPG que deseja usar. Neste exemplo, o ID da chave GPG é `E630A0A00CAA7AAA`.
* Exporte a chave pública:
```bash
gpg --armor --export E630A0A00CAA7AAA
```
* Copie sua chave GPG, começando com `-----BEGIN PGP PUBLIC KEY BLOCK-----` e terminando com `-----END PGP PUBLIC KEY BLOCK-----`.
* Faça login no GitHub ou GitLab e adicione uma nova chave GPG nas configurações:
![Configurações do GitHub](https://i.imgur.com/k64wxvW.png)
![Página de adicionar GPG Key no GitHub](https://i.imgur.com/sMeVvUN.png)
* Defina sua chave de assinatura GPG no Git: (Se quiser adicionar a chave por repositório, omita a flag `--global`)
```bash
git config --global user.signingkey E630A0A00CAA7AAA
```
* Habilite a assinatura automática para todos os commits:
```bash
git config --global commit.gpgsign true
```
* Ou assine por commit usando a opção `-S` no `git commit`:
```bash
git commit -S -m "sua mensagem de commit"
```

Após executar o comando `git commit`, podemos usar o comando `git status` novamente para verificar o status atual:

```bash
git status
```

Saída:

```
On branch main
nothing to commit, working tree clean
```

Como você pode ver, o Git está dizendo que não há alterações para serem commitadas, pois já fizemos o commit delas.

Vamos fazer outra alteração no arquivo `README.md`. Você pode abrir o arquivo com seu editor favorito e fazer a alteração diretamente, ou pode executar o seguinte comando:

```bash
echo "Git é incrível!" >> README.md
```

O comando acima adicionará uma nova linha ao final do arquivo `README.md`. Se executarmos `git status` novamente, veremos a seguinte saída:

```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Como você pode ver, o Git detectou que o arquivo `README.md` foi modificado e também está sugerindo que usemos o comando que aprendemos para primeiro preparar/adicionar o arquivo!

Caso você queira alterar sua última mensagem de commit, pode executar o comando `git commit --amend`. Isso abrirá o editor padrão onde você pode alterar sua mensagem de commit. Também permite alterar as alterações do commit.

O comando `git status` nos dá uma ótima visão geral dos arquivos que foram alterados, mas não mostra quais alterações foram feitas. No próximo capítulo, vamos aprender como verificar as diferenças entre o último commit e as alterações atuais.

Para verificar os commits que alteraram um determinado arquivo, você pode usar a flag `--follow`:

```bash
git log --follow [arquivo]
```

O comando acima mostra os commits que alteraram o arquivo, mesmo em renomeações.
