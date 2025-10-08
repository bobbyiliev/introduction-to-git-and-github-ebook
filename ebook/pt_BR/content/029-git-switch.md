# Git Switch

`git switch` não é uma funcionalidade nova, mas um comando adicional para alternar/trocar de branch, recurso que já estava disponível no comando sobrecarregado `git checkout`. Por isso, recentemente a comunidade Git decidiu publicar um novo comando: `git switch`. Como o nome sugere, ele serve para alternar branches.

### Sintaxe:

```bash
git switch <nome-do-branch>
```

### Visualização do comando:

![git-switch-branch-](https://user-images.githubusercontent.com/55313215/193835157-2981b00b-6b6a-41a2-b34b-37d1bbd89a77.png)

### Diferença entre Switch e Checkout:

Como você pode ver, o uso é bem direto e semelhante ao "git checkout". Mas a grande vantagem sobre o comando "checkout" é que "switch" NÃO tem um milhão de outros significados e capacidades.

Como é um membro relativamente novo da família de comandos do Git, você deve verificar se sua instalação do Git já inclui esse comando.

### Alternar entre dois branches repetidamente

Em alguns cenários, pode ser necessário alternar entre dois branches várias vezes. Em vez de sempre digitar os nomes completos dos branches, você pode simplesmente usar o seguinte atalho:

### Sintaxe:

```bash
git switch -
```

Usando o caractere traço como único parâmetro, o comando "git switch" fará checkout do branch anteriormente ativo. Como dito, isso pode ser muito útil se você precisa ir e voltar entre dois branches várias vezes.
