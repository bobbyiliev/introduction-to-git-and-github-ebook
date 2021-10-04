# Git Configuration

The first time you set up Git on your machine, you would need to do some initial configuration.

There are a few main things that you would need to configure:

* Your details: like your name and email address
* Your Git Editor
* The default branch name: we will learn more about branches later on

We can change all of those things by using the `git config` command.

Let's get started with the initial configuration!

### The `git config` command

In order to configure your Git details like your user name and your email address, you need to use the following command:

* Configuring your Git user name:

```bash
git config --global user.name "Your Name"
```

* Configuring your Git email address:

```bash
git config --global user.email johndoe@example.com
```

> Usually, it is good to have a matching user name and email for your local Git configuration and your GitHub profile details

* Configuring your Git default editor

In some cases, when running Git commands via your terminal, an editor will open where you could type a commit message, for example. To specify your default editor, you need to run the following command:

```bash
git config --global core.editor nano
```

You can change the `nano` editor with another editor like `vim` or `emacs` based on your personal preferences.

* Configuring the default branch name

Whenever creating a new repository on your local machine, it gets initialized with a specific branch name which might be different from the default branch on GitHub. To make sure that the branch name on your local machine matches the default branch name on GitHub, you can use the following command:

```bash
git config --global init.defaultBranch main
```

Finally, once you are done with all changes, you can check your current Git configuration with the following command:

```bash
git config --list
```

Example output:

```
user.name=Bobby Iliev
user.email=bobby@bobbyiliev.com
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
```

### The `~/.gitconfig` file

As we used the `--global` option in our commands, all of those Global Git settings would be stored in a .gitconfig` file inside your home directory.

We can use the `cat` command to check the content of the file:

```bash
cat ~/.gitconfig
```

Example output:

```
[user]
        name = Bobby Iliev
        email = bobby@bobbyiliev.com
```

You can even change the file manually with your favorite text editor, but I personally prefer to use the `git config` command to prevent any syntax problems.

### Repository specific git configurations

So far we have been using the `--global` option with all of our changes to our git configurations and this results in any configuration changes applying to all repositories. You might however want to change the configuration for only one specific repository. 
You can do this easily by running the same git config commands mentioned earlier but with out the `--global` option. This will save the changes for only the respository you are crrently in and leave your global settings the same as they were before. 

### The `.git` directory

Whenever you initialize a new project or clone one from GitHub, it would have a `.git` directory where all of the Git commits would be recorded at and also a `config` file where the configuration settings for the particular project would be stored at.

You could use the `ls` command to check the contents of the `.git` folder:

```bash
ls .git
```

Output:

```
COMMIT_EDITMSG  HEAD  branches  config  description  hooks  index  info  logs  objects  refs
```

> Note: Before running the command, you would need to be inside your project's directory. We will learn about this in the next chapters when we learn more about the `git init` command and cloning an existing repository from GitHub with the `git clone` command.
