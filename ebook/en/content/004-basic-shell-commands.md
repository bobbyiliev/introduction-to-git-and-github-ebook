# Basic Shell Commands

As throughout this eBook, we will be using mainly Git via the command line. It is important to know basic shell commands so that you could find your way around the terminal.

So before we get started, let's go over a few basic shell commands!

### The `ls` command

The `ls` command allows you to list the contents of a folder/directory. All that you need to do in order to run the command is to open a terminal and run the following:

```bash
ls
```

The output will show you all of the files and folders that are located in your current directory. In my case, the output is the following:

```
CONTRIBUTING.md ebook README.md
```

For more information about the `ls` command, make sure to check out this page [here](https://devdojo.com/tnylea/ls-command?ref=bobbyiliev).

> Note: This will work on a Linux/UNIX based systems. If you are on Windows and if you are using the built-in CMD, you would have to use the `dir` command.

### The `cd` command

The `cd` command stands for `Change Directory` and allows you to navigate through the filesystem of your computer or server. Let's say that I wanted to go inside the `ebook` directory from the output above. What I would need to do is to run the `cd` command followed by the directory that I want to access:

```bash
cd ebook
```

If I wanted to go back one level up, I would use the `cd ..` command.

### The `pwd` command

The `pwd` command stands for `Print Working Directory` which essentially means that when you run the command, it will show you the current directory that you are in.

Let's take the example from above. If I run the `pwd` command, I would get the full path to the folder that I'm currently in:

```bash
pwd
```

Output:

```
/home/bobby/introduction-to-git
```

Then I could use the `cd` command and access the `ebook` directory:

```bash
cd ebook
```

And finally, if I was to run the `pwd` command again, I would see the following output:

```
/home/bobby/introduction-to-git/ebook
```

Essentially what happened was that thanks to the `pwd` command, I was able to see that I'm at the `/home/bobby/introduction-to-git` directory and then after accessing the `ebook` directory, again by using `pwd` I was able to see that my new current directory is `/home/bobby/introduction-to-git/ebook`.

### The `rm` command

The `rm` command stands for `remove` and allows you to delete files and folders. Let's say that I wanted to delete the `README.md` file, what I would have to do is run the following command:

```bash
rm README.md
```

In case that I had to delete a folder/directory, I would need to specify the `-r` flag:

```bash
rm -r ebook
```

> Note: keep in mind that the `rm` command would completely delete the files and folders, and the action is irreversible, meaning that you can't get them back.

### The `mkdir` command
The `mkdir` command stands for `make directory` and is used for creating one or more new directories.  All you need to do in order to create a new directory using this command is to open a terminal, `cd` into desired location and run the following:

```bash
mkdir My_New_Directory
```

The above command will create a new, empty directory called `My_New_Directory`.

You can also create serveral new directories by placing the names of desired directories after each other:

```bash
mkdir My_New_Directory My_Another_New_Directory
```

### The `touch` command

The `touch` command is used to update timestamps on files.  A useful feature of the touch command is that it will create an empty file.  This is useful if you want to create file in your directory that doesn't currently exist 

```bash
touch README.md
```
The above will create a new, empty file with the name README.md 

One thing that you need to keep in mind is that all shell commands are case sensitive, so if you type `LS` it would not work.

With that, now you know some basic shell commands which will be beneficial for your day-to-day activities.
