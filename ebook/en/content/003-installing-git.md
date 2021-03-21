# Installing Git

In order for you to be able to use Git on your local machine, you would need to install it.

Depending on the operating system that you are using, you can follow the steps here.

### Install Git on Linux

With most Linux distributions, the Git command-line tool comes installed out of the box.

If this is not the case for you, you can install Git with the following command:

* On RHEL Linux:

```bash
sudo dnf install git-all
```

* On Debian based distributions including Ubuntu:

```bash
sudo apt install git-all
```

### Install Git on Mac

If you are using Mac, Git should be available out of the box as well. However, if this is not the case, there are 2 main ways of installing Git on your Mac:

* Using Homebrew: in case that you are using Homebrew, you can open your terminal and run the following:

```bash
brew install git
```

* Git installer: Alternatively, you could use the following installer:

[git-osx-installer](https://sourceforge.net/projects/git-osx-installer/)

I would personally stick to Homebrew.

### Install Git on Windows

If you have a Windows PC, you can follow the steps on how to install Git on Windows here:

[Install Git on Windows](https://git-scm.com/download/win)

During the installation, make sure to choose the Git Bash option, as this would provide you with a Git Bash terminal which you will use while following along.

### Check Git version

Once you have installed Git, in order to check the version of Git that you have installed on your machine, you could use the following command:

```bash
git --version
```

Example output:

```bash
git version 2.25.1
```

In my case, I have Git 2.25.1 installed on my laptop.