# Configuração do Git

A primeira vez que você configurar o Git na sua máquina, será necessário fazer algumas configurações iniciais.

Há algumas coisas principais que você precisará configurar:

* Seus dados: como nome e endereço de e-mail
* Seu editor do Git
* O nome padrão do branch: aprenderemos mais sobre branches mais adiante

Podemos alterar todas essas configurações usando o comando `git config`.

Vamos começar com a configuração inicial!

### O comando `git config`

Para configurar seus dados do Git, como nome de usuário e endereço de e-mail, use o seguinte comando:

* Configurando seu nome de usuário do Git:

```bash
git config --global user.name "Seu Nome"
```

* Configurando seu endereço de e-mail do Git:

```bash
git config --global user.email seuemail@exemplo.com
```

> Normalmente, é bom ter o mesmo nome de usuário e e-mail na configuração local do Git e no seu perfil do GitHub.

* Configurando o editor padrão do Git

Em alguns casos, ao executar comandos do Git pelo terminal, um editor será aberto para você digitar, por exemplo, uma mensagem de commit. Para especificar seu editor padrão, execute:

```bash
git config --global core.editor nano
```

Você pode trocar o editor `nano` por outro, como `vim` ou `emacs`, conforme sua preferência.

* Configurando o nome padrão do branch

Ao criar um novo repositório na sua máquina local, ele é inicializado com um nome de branch específico, que pode ser diferente do padrão do GitHub. Para garantir que o nome do branch local seja igual ao padrão do GitHub, use:

```bash
git config --global init.defaultBranch main
```

Por fim, após todas as alterações, você pode verificar sua configuração atual do Git com o comando:

```bash
git config --list
```

Exemplo de saída:

```
user.name=Bobby Iliev
user.email=bobby@bobbyiliev.com
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
```

### O arquivo `~/.gitconfig`

Como usamos a opção `--global` nos comandos, todas essas configurações globais do Git ficam armazenadas em um arquivo `.gitconfig` dentro do seu diretório pessoal.

Podemos usar o comando `cat` para ver o conteúdo do arquivo:

```bash
cat ~/.gitconfig
```

Exemplo de saída:

```
[user]
        name = Bobby Iliev
        email = bobby@bobbyiliev.com
```

Você pode até editar o arquivo manualmente com seu editor favorito, mas eu prefiro usar o comando `git config` para evitar problemas de sintaxe.

### Configurações específicas de repositório

Até agora, usamos a opção `--global` em todas as alterações de configuração do git, o que faz com que as mudanças sejam aplicadas a todos os repositórios. No entanto, você pode querer alterar a configuração apenas para um repositório específico.
Para isso, basta executar os mesmos comandos do git config mencionados anteriormente, mas sem a opção `--global`. Assim, as alterações serão salvas apenas para o repositório em que você está, mantendo as configurações globais inalteradas.

### O diretório `.git`

Sempre que você inicializa um novo projeto ou clona um do GitHub, ele terá um diretório `.git` onde todos os commits do Git serão registrados e também um arquivo `config` onde as configurações do projeto específico serão armazenadas.

Você pode usar o comando `ls` para ver o conteúdo da pasta `.git`:

```bash
ls .git
```

Saída:

```
COMMIT_EDITMSG  HEAD  branches  config  description  hooks  index  info  logs  objects  refs
```

> Nota: Antes de executar o comando, você precisa estar dentro do diretório do seu projeto. Aprenderemos sobre isso nos próximos capítulos, quando estudarmos o comando `git init` e como clonar um repositório existente do GitHub com o comando `git clone`.
