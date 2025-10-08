# Git Alias

Se existe um comando Git comum, mas complexo, que você digita com frequência, considere configurar um alias simples para ele. Aliases permitem fluxos de trabalho mais eficientes, exigindo menos teclas para executar um comando. É importante notar que **não existe um comando git alias direto**. Os aliases são criados usando o comando git config e os arquivos de configuração do Git.

```bash
git config --global alias.co checkout
```

Agora, quando eu uso o comando git co, é como se tivesse digitado o comando mais longo git checkout.

```bash
git co -b branch1
```

Saída

```bash
Switched to a new branch 'branch1'
```

Criar aliases não modifica os comandos originais. Então git checkout continuará disponível mesmo que agora tenhamos o alias git co.

```bash
git checkout -b branch2
```

Saída

```bash
Switched to a new branch 'branch2'
```

Aliases também podem ser usados para agrupar uma sequência de comandos Git em um novo comando Git.
