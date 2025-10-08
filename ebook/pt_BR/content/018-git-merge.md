# Git Merge

Quando os desenvolvedores terminam suas alterações, eles podem mesclar seus branches de funcionalidade ao branch principal e tornar essas funcionalidades disponíveis no site.

![Mesclar alterações ao branch principal](https://user-images.githubusercontent.com/21223421/111697237-fd5c4f80-883d-11eb-9506-4347ba482250.png)

Se você seguiu os passos do capítulo anterior, seu branch `novaFuncionalidade` está à frente do branch principal com 1 commit. Para trazer essas novas alterações para o branch principal, precisamos fazer o merge do branch `novaFuncionalidade` no `main`.

### Mesclando um branch

Siga estes passos:

* Primeiro, mude para o branch `main`:

```bash
git checkout main
```

* Depois, para mesclar o branch `novaFuncionalidade` e as alterações que criamos no capítulo anterior, execute:

```bash
git merge novaFuncionalidade
```

Saída:

```
Updating ab1007b..a281d25
Fast-forward
 funcionalidade1.html | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 funcionalidade1.html
```

Como você estava no branch `main` ao rodar o comando, o Git irá pegar todos os commits daquele branch e mesclá-los ao branch principal.

Agora, se rodar o comando `ls`, verá o novo arquivo `funcionalidade1.html`, e se verificar o histórico de commits com `git log`, verá o commit do branch `novaFuncionalidade` presente no branch principal.

Antes de fazer o merge, você pode usar o comando `git diff` para checar as diferenças entre seu branch atual e o branch que deseja mesclar. Por exemplo, se estiver no branch `main`, pode usar:

```bash
git diff novaFuncionalidade
```

Neste caso, o merge ocorreu sem conflitos, pois não havia conflitos. Porém, em projetos reais com várias pessoas, podem ocorrer conflitos. Isso acontece quando alterações são feitas na mesma linha de um arquivo, ou quando um desenvolvedor edita um arquivo em um branch e outro exclui o mesmo arquivo.

### Resolvendo conflitos

Vamos simular um conflito. Para isso, crie um novo branch:

```bash
git checkout -b demoConflito
```

Depois edite o arquivo `funcionalidade1.html`:

```bash
echo "<p>Demonstração de Conflito</p>" >> funcionalidade1.html
```

O comando acima adiciona `<p>Demonstração de Conflito</p>` ao final do arquivo. Você pode verificar o conteúdo com:

```bash
cat funcionalidade1.html
```

Saída:

```
<h1>Meu Primeiro Branch de Funcionalidade</h1>
<p>Demonstração de Conflito</p>
```

Você pode rodar `git status` e `git diff` para ver o que foi modificado antes de fazer o commit.

Depois, faça o commit da alteração:

```bash
git commit -am "Demo de Conflito 1"
```

Note que não usamos o comando `git add`, mas sim a flag `-a`, que significa `add`. Você pode usar isso para arquivos já rastreados pelo git e que foram modificados. Para arquivos novos, é preciso usar `git add` primeiro.

Agora, volte para o branch principal:

```bash
git checkout main
```

Se verificar o arquivo `funcionalidade1.html`, verá apenas a linha `<h1>Meu Primeiro Branch de Funcionalidade</h1>`, pois a alteração feita está apenas no branch `demoConflito`.

Agora, faça uma alteração no mesmo arquivo:

```bash
echo "<p>Conflito: alteração no branch principal</p>" >> funcionalidade1.html
```

Adicionamos uma linha ao final do arquivo com conteúdo diferente.

Prepare e faça o commit da alteração:

```bash
git commit -am "Conflito no main"
```

Agora, tanto o branch principal quanto o branch `demoConflito` têm alterações no mesmo arquivo, na mesma linha. Vamos rodar o comando de merge e ver o que acontece:

```bash
git merge demoConflito
```

Saída:

```
Auto-merging funcionalidade1.html
CONFLICT (content): Merge conflict in funcionalidade1.html
Automatic merge failed; fix conflicts and then commit the result.
```

Como vemos, o merge falhou pois houve alterações no mesmo arquivo, na mesma linha, e o Git não sabe qual alteração é a correta.

Existem várias formas de resolver conflitos. Aqui vamos mostrar uma delas.

Se você verificar o conteúdo do arquivo `funcionalidade1.html`, verá:

```
<h1>Meu Primeiro Branch de Funcionalidade</h1>
<<<<<<< HEAD
<p>Conflito: alteração no branch principal</p>
=======
<p>Demonstração de Conflito</p>
>>>>>>> demoConflito
```

Inicialmente pode parecer confuso, mas vamos revisar:

* `<<<<<<< HEAD`: indica o início das alterações do branch atual. No nosso caso, a linha `<p>Conflito: alteração no branch principal</p>` está no branch principal, que é o branch atual.
* `=======`: indica onde terminam as alterações do branch atual e começam as do novo branch. No nosso caso, a alteração do novo branch é `<p>Demonstração de Conflito</p>`.
* `>>>>>>> demoConflito`: indica o nome do branch de onde vêm as alterações.

Você pode resolver o conflito removendo manualmente as linhas que não são necessárias, deixando o arquivo assim:

```
<h1>Meu Primeiro Branch de Funcionalidade</h1>
<p>Conflito: alteração no branch principal</p>
```

Se estiver usando uma IDE como o VS Code, ela permite escolher quais alterações manter com um clique.

Depois de resolver o conflito, é necessário fazer outro commit:

```bash
git commit -am "Resolver conflito de merge"
```

### Conclusão

Branches e merges do Git permitem que você trabalhe em projetos colaborativos. Uma dica importante é garantir que você puxe as alterações do branch principal local regularmente para não ficar atrás do remoto.

Alguns comandos úteis para quem já está confortável com o que vimos até agora são `git rebase` e `git cherry-pick`, que permitem escolher quais commits de um branch específico você quer trazer para o branch atual.