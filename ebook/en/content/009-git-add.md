# Git Add

By default, when you create a new file inside your Git project, it is not being tracked by Git. So to tell git that it should start tracking the file, you need to use the `git add` command.

The syntax is the following:

```bash
git add NAME_OF_FILE
```

In our case, we have only 1 filed inside our project called `README.md`, so to add this file to Git, we can use the following command:

```bash
git add README.md
```

If you then run `git status` again, you will see a different output:

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

Here you would see that there are now some changes staged and ready to be committed. Also, Git tells us that the `README.md` is a new file that was just staged and has not been tracked before.

In case that you have a couple of files, you could list them all divided by space after the `git add` command to stage them all rather than running `git add` multiple times for each individual file:

```bash
git add file1.html file2.html file3.html
```

With the above, we will add the 3 files by running `git add` just once, however in some cases, you might have a lot of new files, and adding them one by one could be highly time-consuming. 

So there is a way to stage absolutely all files in your current project, and this is by specifying a dot after the `git add` command as follows:

```bash
git add .
```

> Note: You need to be careful with this as in some cases, there might be some files that you don't want to add to Git.

With that, we are ready to move on and learn about the `git commit` command.