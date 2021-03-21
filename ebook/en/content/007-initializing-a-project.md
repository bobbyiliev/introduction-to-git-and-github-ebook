# Initializing a Git project

If you are starting a new project or if you have an existing project which you would like to add to Git and then push to GitHub, you need to initialize a new Git project with the `git init` command.

To keep things simple, let's say that we want to start building a fresh new project. The first thing that I would usually do is to create a new folder where I would store my project files at. To do that, I can use the `mkdir` command followed by the name of the folder, which will create a new empty directory/folder:

```bash
mkdir new-project
```

The above command will create a folder called `new-project`. Then as we learned in chapter 4, we can use the `cd` command to access the directory:

```bash
cd new-project
```

After that, by using the `ls` command, we will be able to verify that the directory is completely empty:

```bash
ls -lah
```

Then with that, we are ready to initialize a new Git project:

```bash
git init
```

You will get the following output:

```
Initialized empty Git repository in /home/devdojo/new-project/.git/
```

As you can see, what the `git init` command does is to create a new `.git` folder which we already discussed in chapter 5.

With that, you've successfully created a new empty Git project! Let's move to the next chapter, where you will learn how to use the `git status` command to check the current status of your repository.