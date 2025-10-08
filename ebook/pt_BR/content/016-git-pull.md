# Git Pull

Se você está trabalhando em um projeto com várias pessoas, é provável que o código mude com frequência. Por isso, você precisa de uma forma de obter as alterações mais recentes do repositório do GitHub para sua máquina local.

Você já sabe que pode usar o comando `git push` para enviar seus commits mais recentes, então, para fazer o oposto e puxar os commits mais recentes do GitHub para o seu projeto local, você precisa usar o comando `git pull`.

Para testar isso, vamos fazer uma alteração diretamente no GitHub. Acesse o arquivo `README.md` e clique no ícone de lápis para editar o arquivo:

![Editar arquivo no GitHub](https://user-images.githubusercontent.com/21223421/111460030-2688bd00-8724-11eb-9569-d6327847b443.png)

Faça uma pequena alteração no arquivo, adicione uma mensagem de commit descritiva e clique no botão `Commit Changes`:

![Commit via GitHub](https://user-images.githubusercontent.com/21223421/111460194-5afc7900-8724-11eb-9c43-a8952961fca8.png)

Com isso, você fez um commit diretamente no GitHub, então seu repositório local ficará desatualizado em relação ao remoto.

Se você tentar enviar uma alteração agora para esse mesmo branch, irá falhar com o seguinte erro:

```
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'git@github.com:bobbyiliev/demo-repo.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

Como informado na saída, o repositório remoto está à frente do seu local, então você precisa rodar o comando `git pull` para obter as alterações mais recentes:

```bash
git pull origin main
```

A saída será parecida com esta:

```
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 646 bytes | 646.00 KiB/s, done.
From github.com:bobbyiliev/demo-repo
 * branch            main       -> FETCH_HEAD
   da46ce3..442afa5  main       -> origin/main

 README.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

Podemos ver que o arquivo `README.md` foi alterado e que houve 2 novas linhas adicionadas e 1 linha removida.

Agora, se você rodar `git log`, verá o commit que fez no GitHub disponível localmente.

Claro, este é um cenário simplificado. No mundo real, você não faria alterações diretamente no GitHub, mas provavelmente trabalharia com outras pessoas no mesmo projeto e teria que puxar as alterações delas regularmente.

Você precisa garantir que puxa as alterações mais recentes sempre antes de tentar enviar suas próprias alterações.

Agora que você conhece os comandos básicos do Git, vamos aprender o que são Branches no Git.
