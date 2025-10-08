# Comandos Básicos do Shell

Como ao longo deste eBook usaremos principalmente o Git via linha de comando, é importante conhecer comandos básicos do shell para que você possa se orientar no terminal.

Então, antes de começarmos, vamos revisar alguns comandos básicos do shell!

### O comando `ls`

O comando `ls` permite listar o conteúdo de uma pasta/diretório. Para executar o comando, basta abrir o terminal e rodar o seguinte:

```bash
ls
```

A saída mostrará todos os arquivos e pastas que estão localizados no seu diretório atual. No meu caso, começando pelo diretório raiz deste projeto, a saída é a seguinte:

```
CONTRIBUTING.md LICENSE README.md ebook index.html
```

Pela saída, podemos ver que `CONTRIBUTING.md`, `LICENSE`, `README.md`, `index.html` são arquivos, enquanto `ebook` é um subdiretório/subpasta.

Para mais informações sobre o comando `ls`, confira esta página [aqui](https://devdojo.com/tnylea/ls-command?ref=bobbyiliev).

> Nota: Isso funciona em sistemas Linux/UNIX. Se você estiver no Windows e usando o CMD padrão, deve usar o comando `dir`.

### O comando `cd`

O comando `cd` significa `Change Directory` (Mudar Diretório) e permite navegar pelo sistema de arquivos do seu computador ou servidor. Suponha que eu queira entrar no diretório `ebook` da saída acima. Basta rodar o comando `cd` seguido do diretório que quero acessar:

```bash
cd ebook
```

Se eu quiser voltar um nível, uso o comando `cd ..`. Assim, volto um nível acima do diretório `ebook`, retornando ao diretório raiz do projeto.

### O comando `pwd`

O comando `pwd` significa `Print Working Directory` (Imprimir Diretório Atual), ou seja, ao rodar o comando, ele mostra o diretório em que você está.

No exemplo acima, se eu rodar o comando `pwd`, terei o caminho completo da pasta em que estou:

```bash
pwd
```

Saída:

```
/home/bobby/introduction-to-git
```

Depois posso usar o comando `cd` para acessar o diretório `ebook`:

```bash
cd ebook
```

E, se rodar o comando `pwd` novamente, verei a seguinte saída:

```
/home/bobby/introduction-to-git/ebook
```

Ou seja, graças ao comando `pwd`, pude ver que estava no diretório `/home/bobby/introduction-to-git` e, após acessar o diretório `ebook`, usando novamente o `pwd`, vi que meu novo diretório atual é `/home/bobby/introduction-to-git/ebook`.

### O comando `rm`

O comando `rm` significa `remove` (remover) e permite excluir arquivos e pastas. Suponha que eu queira excluir o arquivo `README.md`, basta rodar:

```bash
rm README.md
```

Caso precise excluir uma pasta/diretório, é necessário especificar a flag `-r`:

```bash
rm -r ebook
```

> Nota: lembre-se que o comando `rm` exclui completamente os arquivos e pastas, e a ação é irreversível, ou seja, não tem como recuperá-los.

### O comando `mkdir`

O comando `mkdir` significa `make directory` (criar diretório) e é usado para criar um ou mais novos diretórios. Para criar um novo diretório, basta abrir o terminal, navegar até o local desejado com `cd` e rodar:

```bash
mkdir Minha_Nova_Pasta
```

O comando acima criará um novo diretório vazio chamado `Minha_Nova_Pasta`.

Você também pode criar vários diretórios de uma vez, colocando os nomes desejados um após o outro:

```bash
mkdir Minha_Nova_Pasta Minha_Outra_Nova_Pasta
```

### O comando `touch`

O comando `touch` é usado para atualizar o timestamp dos arquivos. Uma funcionalidade útil do comando touch é que ele cria um arquivo vazio. Isso é útil se você quiser criar um arquivo no diretório que ainda não existe:

```bash
touch README.md
```
O comando acima criará um novo arquivo vazio chamado README.md.

Uma coisa importante é que todos os comandos do shell são sensíveis a maiúsculas e minúsculas, então se você digitar `LS` não irá funcionar.

Com isso, agora você conhece alguns comandos básicos do shell que serão úteis no seu dia a dia.
