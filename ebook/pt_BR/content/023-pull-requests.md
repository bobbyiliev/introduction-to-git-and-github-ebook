# Pull Requests

Você já sabe como mesclar alterações de um branch para outro no seu repositório Git local.

Para fazer o mesmo no GitHub, você precisa abrir um Pull Request (ou Merge Request, se estiver usando GitLab), ou PR para abreviar, e solicitar a mesclagem do seu branch de funcionalidade para o branch `main`.

Os passos para abrir um Pull Request são:

* Se você está trabalhando em um projeto open source do qual não é mantenedor, primeiro faça um fork do repositório conforme explicado no capítulo 21. Pule esta etapa se você for o mantenedor do repositório.
* Depois, clone o repositório localmente com o comando `git clone`:

```bash
git clone git@github.com:seu_usuario/seu_repositorio
```

* Crie um novo branch com o comando `git checkout`:

```bash
git checkout -b nome_do_branch
```

* Faça suas alterações no código

* Prepare as alterações com `git add`:

```bash
git add .
```

* E então faça o commit com `git commit`:

```bash
git commit -m "Mensagem do Commit"
```

* Depois envie seu novo branch para o GitHub com `git push`:

```bash
git push origin nome_do_branch
```

* Após isso, acesse o repositório no GitHub e clique no botão `Pull Requests` e depois no botão verde `New pull request`:

![Pull request](https://user-images.githubusercontent.com/21223421/111886569-409df600-89d7-11eb-87d5-88c935ef09b2.png)

* Lá, escolha o branch para o qual deseja mesclar e o branch de onde deseja mesclar:

![Git Pull Request Compare](https://user-images.githubusercontent.com/21223421/111886583-675c2c80-89d7-11eb-8069-68a086dbc539.png)

* Depois revise as alterações, adicione um título e descrição e clique no botão de criar.
* Se estiver trabalhando em um projeto com múltiplos colaboradores, selecione alguns revisores. Revisores são pessoas que você gostaria que revisassem seu código antes de ele ser mesclado ao branch `main`.

Para uma representação visual de todo o processo, confira este tutorial passo a passo:

* [Como enviar seu primeiro Pull Request no GitHub](https://www.digitalocean.com/community/tutorials/hacktoberfest-how-to-submit-your-first-pull-request-on-github)
