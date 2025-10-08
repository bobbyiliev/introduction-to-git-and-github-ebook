# Git Rebase

O rebase é frequentemente usado como alternativa ao merge. Fazer rebase em um branch atualiza um branch com outro, aplicando os commits de um branch sobre os commits de outro branch. Por exemplo, se você está trabalhando em um branch de funcionalidade que está desatualizado em relação ao branch dev, fazer rebase do branch de funcionalidade sobre o dev permitirá que todos os novos commits do dev sejam incluídos na funcionalidade. Veja como isso fica visualmente:

### Visualização do comando:
![image](https://user-images.githubusercontent.com/54790525/138965417-52f36e80-fbd1-4eaa-8914-1a228988c4f4.png)
![image](https://user-images.githubusercontent.com/54790525/138965429-87265772-b89a-4a31-9deb-3a902d885540.png)

### Sintaxe:
```bash
git rebase feature dev
```
onde branch1 é o branch que queremos fazer rebase para o master.

### Diferença entre Merge e Rebase:
Muitas pessoas acham que os comandos `Merge` e `Rebase` fazem o mesmo trabalho, mas na verdade são completamente diferentes e vamos discutir isso a seguir.

-  #### Merge:
  Este comando é usado para integrar alterações de um branch para outro, mantendo o branch mesclado como base, assim você pode facilmente retornar a uma versão anterior do código se quiser. A imagem abaixo mostra isso:
  ![Merge](https://i.imgur.com/jD4yhZ5.png)

### Uso típico do rebase
#### Atualizando um Branch de Funcionalidade
Vamos supor que você está trabalhando em um branch de funcionalidade, focado no seu trabalho.
![image](https://user-images.githubusercontent.com/54790525/138965621-337737eb-6758-4556-891b-54795a4735df.png)

Então você percebe que há novos commits no dev que gostaria de ter no seu branch de funcionalidade, já que esses novos commits podem afetar como você implementa a funcionalidade.

![image](https://user-images.githubusercontent.com/54790525/138965666-88f517f6-2906-4c7e-8937-e53404812c21.png)

Você decide rodar git rebase dev a partir do seu branch de funcionalidade para ficar atualizado com o dev.
No entanto, ao rodar o comando rebase, há alguns conflitos entre as alterações que você fez na funcionalidade e os novos commits no dev. Felizmente, o processo de rebase passa por cada commit um de cada vez e, assim que percebe um conflito em um commit, o git fornece uma mensagem no terminal indicando quais arquivos precisam ser resolvidos. Depois de resolver o conflito, você usa git add para adicionar suas alterações ao commit e roda git rebase --continue para continuar o processo de rebase. Se não houver mais conflitos, você terá feito o rebase do seu branch de funcionalidade sobre o dev com sucesso.

![image](https://user-images.githubusercontent.com/54790525/138965979-f207053e-afcf-49a6-a392-fe4fd530011a.png)

Agora você pode continuar trabalhando na sua funcionalidade com os commits mais recentes do dev incluídos, e tudo está bem novamente. Esse processo pode se repetir se o branch dev for atualizado com novos commits.

- #### Rebase:
  Por outro lado, o comando `Rebase` é usado para transferir a base do branch para ser baseada no último commit do branch atual, tornando-os como um só branch, como mostrado na imagem acima.

### Rebase interativo:

Você também pode fazer rebase de um branch sobre outro de forma `interativa`. Isso significa que você será solicitado a escolher opções.
O comando básico é:

```bash
git rebase -i feature main
```

Isso abrirá seu editor favorito (provavelmente `vi` ou `vscode`).

Vamos criar um exemplo:

```bash
git switch main
git checkout -b feature-interactive
echo "<p>Rebasing interactively is super cool</p>" >> feature1.html
git commit -am "Commit to test Interactive Rebase"
echo "<p>With interactive rebasing you can do really cool stuff</p>" >> feature1.html
git commit -am "Commit to test Interactive Rebase"
```

Agora você está no branch `feature-interactive` com um commit que não existe no branch `main`, e há um novo commit no `main` que não está no seu branch.

Agora usando o comando de rebase interativo:

```bash
git rebase -i main
```

Seu editor favorito (`vi` aqui ou `vscode` se configurado corretamente) deve abrir algo assim:

```
pick a21b178 Commit to test Interactive Rebase
pick cd3400c Commit to test Interactive Rebase

# Rebase 1d152d4..a21b178 onto 1d152d4
#
# p, pick <commit> = usar o commit
# r, reword <commit> = usar o commit, mas editar a mensagem do commit
# e, edit <commit> = usar o commit, mas parar para alterar
# s, squash <commit> = usar o commit, mas mesclar ao commit anterior
# f, fixup <commit> = como "squash", mas descarta a mensagem do commit
# x, exec <command> = rodar comando (restante da linha) usando shell
# b, break = parar aqui (continuar rebase depois com 'git rebase --continue')
# d, drop <commit> = remover commit
# l, label <label> = marcar HEAD atual com um nome
# t, reset <label> = resetar HEAD para um label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       criar um commit de merge usando a mensagem do commit original
# .       (ou o oneline, se não houver commit original).
# .       Use -c <commit> para editar a mensagem do commit.
#
# Essas linhas podem ser reordenadas; são executadas de cima para baixo.
#
# Se você remover uma linha aqui, ESSE COMMIT SERÁ PERDIDO.
#
# Se remover tudo, o rebase será abortado.
#
# Commits vazios são comentados
```

Como pode ver, as primeiras linhas são os commits feitos nesse branch `feature-interactive`. O restante do arquivo é a mensagem de ajuda.
Se olhar atentamente para essa mensagem de ajuda, verá que há várias opções. Para usá-las, basta prefixar a linha do commit que deseja trabalhar com o nome do comando ou sua letra de atalho.

O comando básico é `pick`, que significa que o rebase atual usará esses dois commits para fazer seu trabalho.

No nosso caso, se quiser atualizar a mensagem do segundo commit, basta atualizar o arquivo assim (mostramos só as primeiras linhas):

```
pick a21b178 Commit to test Interactive Rebase
r cd3400c Commit to test Interactive Rebase

# Rebase 1d152d4..a21b178 onto 1d152d4
#
...
```

Depois salve o arquivo, se for `vi`, pressione `:` e digite `wq`. Você verá outro arquivo aberto no mesmo editor, onde pode editar sua mensagem de commit, salvar e pronto.

Você pode ver o resultado com o comando:

```bash
git log
```

Agora que você sabe o básico de como usar esse comando, dê uma olhada na mensagem de ajuda. Existem comandos úteis ali. Meus favoritos são `reword`, `fixup` e `drop`, mas sinta-se livre para experimentar por conta própria.
