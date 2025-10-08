# Revertendo alterações

Como em tudo, existem várias maneiras de fazer uma determinada coisa. Mas o que eu normalmente faço quando quero desfazer meu último commit e então commitar minhas novas alterações é o seguinte.

* Suponha que você fez algumas alterações e realizou o commit:

```bash
git commit -m "Commitando alterações erradas"
```

* Depois disso, se você rodar `git log`, verá o histórico de tudo que foi commitado no repositório.

* Infelizmente, após o commit das alterações erradas, você percebe que esqueceu de adicionar arquivos ao commit ou esqueceu de fazer uma pequena alteração nos arquivos já commitados.

* Para resolver isso, basta fazer essas alterações e prepará-las com `git add`, então você pode "amendar" o último commit rodando o seguinte comando:

```bash
git commit --amend
```

**Nota:** O comando acima também permite alterar a mensagem do commit, se necessário.

## Resetando alterações (⚠️ Resetar é perigoso ⚠️)

> É preciso ter cuidado com comandos de reset, pois eles apagam commits do repositório e os removem do histórico.

Exemplo:
```bash
git reset --soft HEAD~1
```

O comando acima irá resetar voltando 1 commit.

**Nota:** O comando acima desfaz seu commit, mas mantém as alterações no código. Se quiser se livrar das alterações também, faça um reset hard: `git reset --hard HEAD~1`

Sintaxe:
```bash
git reset [--soft|--hard] [<referência-do-commit>]
```

* Depois disso, faça suas novas alterações

* Quando terminar, rode `git add` para adicionar os arquivos que deseja incluir no próximo commit:

```bash
git add .
```

* Em seguida, use `git commit` normalmente para commitar suas novas alterações:

```bash
git commit -m "Sua nova mensagem de commit"
```

* Depois disso, você pode novamente verificar o histórico rodando:

```bash
git log
```

Aqui está um exemplo do processo:

![Git Como desfazer o último commit digitalocean](https://i.imgur.com/L5zOGG1.png)

**Nota:** Você pode resetar suas alterações voltando mais de um commit usando a seguinte sintaxe:
```bash
git reset --soft HEAD~n
```
onde `n` é o número de commits que você quer voltar.

Outra abordagem seria usar `git revert COMMIT_ID`.

Aqui está um vídeo rápido demonstrando como fazer isso:

[Revertendo alterações](https://www.youtube.com/watch?v=54Hy6KnfbuY)
