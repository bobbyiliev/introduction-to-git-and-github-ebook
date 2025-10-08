# Git Log

Para listar todos os commits anteriores, você pode usar o seguinte comando:

```bash
git log
```

Isso fornecerá o histórico de commits, e a saída será parecida com esta:

```
commit da46ce39a3fd663ff802d013f834431d4b4159a5 (HEAD -> main)
Author: Bobby Iliev <bobby@bobbyiliev.com>
Date:   Fri Mar 12 17:14:02 2021 +0000

    Atualizar README.md

commit fa583473b4be2807b45f35b755aa84ac78922259
Author: Bobby Iliev <bobby@bobbyiliev.com>
Date:   Fri Mar 12 17:01:17 2021 +0000

    Commit inicial
```

As entradas são listadas, em ordem, da mais recente para a mais antiga.

Resumo da saída:

* `commit da46ce39a3fd663ff802d013f834431d4b4159a5`: Aqui você pode ver o ID específico do commit
* `Author: Bobby Iliev...`: Depois você vê quem criou as alterações
* `Date:   Fri Mar 12...`: Em seguida, você tem a data e hora exata em que o commit foi criado
* Por fim, você tem a mensagem do commit. Por isso é importante escrever mensagens curtas e descritivas, para que depois você possa saber quais alterações foram introduzidas por cada commit.

Se quiser verificar as diferenças entre o estado atual do seu repositório e um commit específico, basta usar o comando `git diff` seguido do ID do commit:

```bash
git diff fa583473b4be2807b45f35b755aa84ac78922259
```

No meu caso, a saída será a seguinte:

```
diff --git a/README.md b/README.md
index 9366068..2b14655 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,2 @@
 # Projeto Demo
+Git é incrível
```

Portanto, a diferença entre esse commit específico e o estado atual do repositório é a alteração no arquivo `README.md`.

Caso queira ver apenas os IDs dos commits e as mensagens em uma linha, você pode adicionar o argumento `--oneline`:

```bash
git log --oneline
```

Saída:

```
* da46ce3 (HEAD -> main) Atualizar README.md
* fa58347 Commit inicial
```

Com isso, agora você sabe como verificar o histórico de commits! No próximo capítulo, vamos aprender como excluir arquivos específicos do Git!
