# Git Stash

`git stash` é um comando útil que ajuda em situações em que você precisa guardar temporariamente suas alterações locais e resetar seu código para o commit mais recente, para trabalhar em um bug ou funcionalidade mais urgente.

Em outras palavras, esse comando permite reverter seu diretório de trabalho para coincidir com o commit `HEAD`, mantendo todas as modificações locais salvas.

Quando estiver pronto para voltar ao código que guardou, basta restaurá-lo com um único comando!

## Guardando seu trabalho

```bash
git stash
```

Por exemplo, considere um arquivo chamado `index.html` que foi modificado desde o último commit.

![git-stash-example](https://user-images.githubusercontent.com/42696800/136789285-ca33c54c-7f58-465a-a6c8-49d2d541a422.png)

Note que ao rodar o comando `git status` após o comando `git stash`, não há mais alterações pendentes!

Aqui, WIP significa Work-In-Progress e é usado para indexar as várias cópias guardadas do seu trabalho.

Um ponto importante antes de guardar todas as alterações é que, por padrão, o `git stash` **não guarda arquivos não rastreados e ignorados.** (Arquivos não rastreados são aqueles que não faziam parte do último commit, ou seja, arquivos novos no seu repositório local)

Se quiser incluir esses arquivos não rastreados no stash, use a opção **-u**.

```bash
git stash -u
```

Da mesma forma, todos os arquivos listados no `.gitignore` (arquivos ignorados) também serão excluídos do stash. Para incluí-los, use a opção **-a**:

```bash
git stash -a
```

As ilustrações abaixo mostram o comportamento do comando `git stash` quando essas opções são usadas:

![git-stash-options](https://user-images.githubusercontent.com/42696800/136953468-8bbcbc7e-54e3-4927-b3e7-9ebd96db0fe2.png)

## Restaurando as alterações guardadas

```bash
git stash apply
```

Esse comando é usado para reaplicar todas as modificações locais feitas antes de guardar o trabalho.

Outro comando que pode ser usado para isso é o `git stash pop`. Aqui, "pop" significa remover o conteúdo mais recente do stash e reaplicá-lo ao seu diretório de trabalho.

A diferença entre os dois comandos é que o `git stash pop` **remove essas alterações do stash**, enquanto o `git stash apply` **mantém as alterações guardadas** mesmo após restaurá-las.

Considere o exemplo anterior, em que o arquivo `index.html` foi guardado. Na imagem abaixo, você vê como restaurar essas alterações afeta seu repositório local.

![git-stash-apply](https://user-images.githubusercontent.com/42696800/136791882-c43f5805-354c-47f1-8866-959d519a932e.png)

Mas e se você tiver vários stashes e não souber qual deseja restaurar? É aí que entra o próximo comando!

## Lidando com múltiplas cópias guardadas do seu trabalho

Assim como ao resetar o repositório local para um commit específico, o primeiro passo para lidar com múltiplos stashes é **ver as várias cópias guardadas disponíveis**.

```bash
git stash list
```

Esse comando mostra uma lista indexada de todos os stashes disponíveis junto com uma **mensagem correspondente ao commit recente**.

Veja o exemplo abaixo, onde há dois stashes disponíveis: um quando um novo arquivo de script foi adicionado e outro quando esse arquivo foi alterado.

![git-stash-2](https://user-images.githubusercontent.com/42696800/136959951-cee9e074-7132-4b3b-82fb-9ac28c80cce7.png)

Note que o stash mais recente sempre tem o índice 0.

Depois de saber qual stash deseja restaurar, use o comando:

```bash
git stash apply n
```

Ou, alternativamente:

```bash
git stash apply "stash@{n}"
```

Aqui, **n** é o índice do stash que você quer restaurar.
