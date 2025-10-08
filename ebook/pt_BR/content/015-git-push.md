# Git Push

Por fim, depois de fazer todas as suas alterações, prepará-las com o comando `git add .` e realizar o commit com o comando `git commit`, você deve enviar (push) as alterações commitadas do seu repositório local para o repositório remoto no GitHub. Isso garante que o repositório remoto fique atualizado com o seu repositório local.

## Criando e vinculando um repositório remoto

Antes de poder enviar para seu repositório remoto no GitHub, você precisa primeiro criar o repositório remoto pelo GitHub, conforme explicado no Capítulo 6.

Depois de ter seu repositório remoto pronto no GitHub, você pode adicioná-lo ao seu projeto local com o seguinte comando:

```bash
git remote add origin git@github.com:seu_usuario/seu_nome_repositorio.git
```

> Nota: Certifique-se de alterar os detalhes `seu_usuario` e `seu_nome_repositorio` conforme necessário.

Assim você vincula seu projeto Git local ao repositório remoto no GitHub.

Se você leu o capítulo anterior, provavelmente percebeu que estamos usando SSH como método de autenticação.

No entanto, se você não seguiu os passos do capítulo anterior, pode usar HTTPS em vez de SSH:

```bash
git remote add origin https://github.com/seu_usuario/seu_nome_repositorio.git
```

Para verificar seu repositório remoto, execute o comando:

```bash
git remote -v
```

## Enviando commits

Para enviar suas alterações commitadas para o repositório remoto vinculado, use o comando `git push`:

```bash
git push -u origin main
```
> Nota: Neste comando, `-u origin main` diz ao Git para definir o branch main do repositório remoto como o branch upstream no comando `git push`. Isso é uma boa prática ao usar Git, pois permite que os comandos `git push` e `git pull` funcionem como esperado. Alternativamente, você pode usar `--set-upstream origin main` para isso também.

Se estiver usando SSH com sua chave SSH cadastrada no GitHub, o comando push não pedirá senha e enviará suas alterações diretamente para o GitHub.

Caso você não tenha executado o comando `git remote add` como mostrado anteriormente, receberá o seguinte erro:

```
fatal: 'origin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

Isso significa que você não adicionou seu repositório do GitHub como repositório remoto. Por isso, usamos o comando `git remote add` para criar essa conexão entre seu repositório local e o remoto.

Note que a conexão já estará configurada se você usou o comando `git clone` para clonar um repositório existente do GitHub para sua máquina local. Vamos abordar o comando `git pull` nos próximos capítulos.

## Verificando o repositório remoto

Após executar o comando `git push`, você pode acessar seu projeto no GitHub e verá os commits que fez localmente presentes no repositório remoto. Se clicar no link de `commits`, poderá ver todos os commits, assim como se tivesse executado o comando `git log`:

![Commits no GitHub](https://user-images.githubusercontent.com/21223421/111459731-c1cd6280-8723-11eb-996f-5982879f811b.png)

Agora que você sabe como enviar suas últimas alterações do seu projeto Git local para o repositório no GitHub, é hora de aprender como puxar as alterações mais recentes do GitHub para o seu projeto local.
