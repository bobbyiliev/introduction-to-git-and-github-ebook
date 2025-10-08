# Instalando o Git

Para que você possa usar o Git em sua máquina local, será necessário instalá-lo.

Dependendo do sistema operacional que você está usando, siga os passos abaixo.

### Instalar o Git no Linux

Na maioria das distribuições Linux, a ferramenta de linha de comando do Git já vem instalada por padrão.

Se esse não for o seu caso, você pode instalar o Git com o seguinte comando:

* No RHEL Linux:

```bash
sudo dnf install git-all
```

* Em distribuições baseadas no Debian, incluindo Ubuntu:

```bash
sudo apt install git-all
```

### Instalar o Git no Mac

Se você estiver usando Mac, o Git também deve estar disponível por padrão. No entanto, se não estiver, há 2 principais formas de instalar o Git no seu Mac:

* Usando o Homebrew: caso você utilize o Homebrew, abra o terminal e execute:

```bash
brew install git
```

* Instalador do Git: alternativamente, você pode usar o seguinte instalador:

[git-osx-installer](https://sourceforge.net/projects/git-osx-installer/)

Pessoalmente, recomendo usar o Homebrew.

### Instalar o Git no Windows

Se você tem um PC com Windows, siga os passos para instalar o Git no Windows aqui:

[Instalar Git no Windows](https://git-scm.com/download/win)

Durante a instalação, certifique-se de escolher a opção Git Bash, pois ela fornecerá um terminal Git Bash que você usará ao acompanhar o conteúdo.

### Verificar a versão do Git

Depois de instalar o Git, para verificar a versão instalada em sua máquina, utilize o seguinte comando:

```bash
git --version
```

Exemplo de saída:

```bash
git version 2.25.1
```

No meu caso, tenho o Git 2.25.1 instalado no meu laptop.
