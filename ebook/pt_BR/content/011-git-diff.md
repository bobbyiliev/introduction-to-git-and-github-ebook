# Git Diff

Como mencionado no capítulo anterior, o comando `git status` nos dá uma ótima visão geral dos arquivos que foram alterados, mas não mostra quais alterações foram feitas.

Você pode verificar as alterações reais feitas com o comando `git diff`. Se executarmos o comando em nosso repositório, veremos a seguinte saída:

```
diff --git a/README.md b/README.md
index 9366068..2b14655 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,2 @@
 # Projeto Demo
+Git é incrível
```

Como só alteramos o arquivo `README.md`, o Git está mostrando o seguinte:

* `diff --git a/README.md b/README.md`: aqui o git indica que está mostrando as alterações feitas no arquivo `README.md` desde o último commit em comparação com a versão atual do arquivo.
* `@@ -1 +1,2 @@`: aqui o git indica que 1 nova linha foi adicionada
* `+Git é incrível`: aqui, o importante é o `+`, que indica que esta é uma nova linha que foi adicionada. Caso você remova uma linha, verá um sinal de `-` em vez disso.

No nosso caso, como só adicionamos 1 nova linha ao arquivo, o Git indica que apenas 1 arquivo foi alterado e que apenas 1 nova linha foi adicionada.

Em seguida, vamos preparar essa alteração e fazer o commit com os comandos que aprendemos nos capítulos anteriores!

* Prepare o arquivo alterado:

```bash
git add README.md
```

* Execute novamente o `git status` para verificar o status atual:

```bash
git status
```

A saída será parecida com esta, indicando que há 1 arquivo modificado:

```
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
```

* Faça o commit das alterações:

```bash
git commit -m "Atualizar README.md"
```

Por fim, se você executar `git status` novamente verá que não há alterações para serem commitadas.

Eu sempre executo `git status` e `git diff` antes de fazer qualquer commit, só para ter certeza do que foi alterado.

> Nota 1: `git diff --staged` mostrará apenas as alterações dos arquivos na área de "staged".

> Nota 2: `git diff HEAD` mostrará todas as alterações em arquivos rastreados (arquivos do último snapshot). Se todas as alterações estiverem preparadas para commit, ambos os comandos darão a mesma saída.

Em alguns casos, você pode querer ver uma lista dos commits anteriores. Vamos aprender como fazer isso no próximo capítulo.
