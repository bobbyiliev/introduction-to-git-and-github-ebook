# Branches do Git

Até agora, trabalhamos apenas no nosso branch Main, que é criado por padrão ao criar um novo repositório no GitHub. Neste capítulo, você aprenderá mais sobre branches no Git, por que eles são necessários e como trabalhar com eles.

A definição oficial de branch do Git, segundo o site git-scm.com, é a seguinte:

> Um branch no Git é simplesmente um ponteiro leve e móvel para um desses commits.

Isso pode ser um pouco confuso se você está começando agora. Então, pense nos branches como uma forma de trabalhar em seu projeto adicionando uma nova funcionalidade ou corrigindo bugs sem afetar o branch Main.

Assim, cada nova funcionalidade ou correção de bug que você estiver desenvolvendo pode viver em um branch separado e, depois que estiver pronto e tiver testado as alterações, você pode mesclar o novo branch ao branch principal. Você aprenderá mais sobre merge no próximo capítulo!

Se olharmos para a ilustração abaixo, onde temos alguns branches, você verá que parece uma árvore, daí o termo "branching":

![Branches do Git](https://user-images.githubusercontent.com/21223421/111696461-03056580-883d-11eb-82c4-7f8d926629e6.png)

Graças aos múltiplos branches, várias pessoas podem trabalhar em diferentes funcionalidades ou correções ao mesmo tempo, cada uma em seu próprio branch.

A imagem mostra 3 branches:

* O branch principal (main)
* Novo Branch 1
* Novo Branch 2

O branch principal é o branch padrão, que você já conhece. Podemos considerar os outros dois branches como duas novas funcionalidades que estão sendo desenvolvidas. Um desenvolvedor pode estar trabalhando em um novo formulário de contato para sua aplicação web no branch #1, e outro pode estar desenvolvendo uma funcionalidade de cadastro de usuários no branch #2.

Graças aos branches separados, ambos podem trabalhar no mesmo projeto sem atrapalhar um ao outro.

Agora, vamos aprender como criar novos branches e ver isso na prática!

### Criando um novo branch

Vamos começar criando um novo branch chamado `novaFuncionalidade`. Para criar o branch, use o comando:

```bash
git branch novaFuncionalidade
```

Agora, para mudar para esse novo branch, execute:

```bash
git checkout novaFuncionalidade
```

> Nota: Você pode usar o comando `git checkout` para alternar entre diferentes branches.

Os dois comandos acima podem ser combinados em um só, assim você não precisa criar o branch primeiro e depois mudar para ele. Use este comando:

```bash
git checkout -b novaFuncionalidade
```

Ao executar esse comando, verá a seguinte saída:

```
Switched to a new branch 'novaFuncionalidade'
```

Para verificar em qual branch você está atualmente, use:

```bash
git branch
```

Saída:

```
  main
* novaFuncionalidade
```

Podemos ver que temos 2 branches: o `main` e o `novaFuncionalidade` que acabamos de criar. O asterisco antes do nome indica que estamos atualmente no branch `novaFuncionalidade`.

Se você usar o comando `git checkout` para voltar ao branch `main`:

```bash
git checkout main
```

E rodar `git branch` novamente, verá:

```
* main
  novaFuncionalidade
```

### Fazendo alterações no novo branch

Agora vamos fazer uma alteração no branch de nova funcionalidade. Primeiro, mude para o branch com o comando:

```bash
git checkout novaFuncionalidade
```

> Nota: só é necessário usar o argumento `-b` ao criar novos branches.

Verifique se você está no branch correto:

```bash
git branch
```

Saída:

```
  main
* novaFuncionalidade
```

Agora, crie um novo arquivo com conteúdo de demonstração:

```bash
echo "<h1>Meu Primeiro Branch de Funcionalidade</h1>" > funcionalidade1.html
```

O comando acima irá criar o arquivo `funcionalidade1.html` com o conteúdo `<h1>Meu Primeiro Branch de Funcionalidade</h1>`.

Depois disso, prepare o arquivo e faça o commit:

```bash
git add funcionalidade1.html
git commit -m "Adicionar funcionalidade1.html"
```

O novo arquivo estará presente apenas no branch `novaFuncionalidade`. Se você mudar para o branch `main` e rodar o comando `ls` ou verificar o `git log`, verá que o arquivo não está lá.

Você pode verificar isso usando:

```bash
git log
```

Com isso, usamos vários dos comandos que vimos nos capítulos anteriores!

### Comparando branches

Você também pode comparar dois branches com os comandos abaixo.

* Mostra os commits em `branchA` que não estão em `branchB`:

```bash
git log BranchA..BranchB
```

* Mostra as diferenças do que está em `branchA` mas não em `branchB`:

```bash
git diff BranchB...BranchA
```

### Renomeando um branch

Se você criou um branch com o nome errado ou acha que o nome pode ser melhor, pode renomear com:

```bash
git branch -m nome-antigo nome-novo
```

Se quiser renomear o **branch atual**, basta rodar:

```bash
git branch -m nome-do-branch
```

Depois, se rodar `git branch` novamente, verá o nome correto.

### Excluindo um branch

Para excluir um branch específico, execute:

```bash
git branch -d nome_do_branch
```

Isso exclui o branch apenas do seu repositório local. Se já tiver enviado o branch para o GitHub, use:

```bash
git push origin --delete nome_do_branch
```

Se quiser sincronizar seus branches locais com os remotos, rode:

```bash
git fetch
```

### Conclusão

Com isso, nosso branch `novaFuncionalidade` está à frente do branch principal com 1 commit. Para trazer essas novas alterações para o branch principal, precisamos fazer o merge do branch `novaFuncionalidade` no `main`.

No próximo capítulo, você aprenderá como mesclar suas alterações de um branch para outro!

Uma coisa importante: antigamente, ao criar um novo repositório no GitHub, o nome padrão do branch era `master`. Agora, novos repositórios usam `main` como padrão, como parte do esforço do GitHub para usar termos mais inclusivos.