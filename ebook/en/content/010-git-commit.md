# Git Commit

Once you have added/staged your files, the next step is to actually commit the changes. So if you run `git status` again you will be able to see that Git tells use that there are changes to be commited:

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

In this case it is only the `README.md` file that will be commited. So in order to do so, we can run the following command:

```
git commit -m "Your Commit Message Here"
```

Rundown of the command:

* `git commit`: here we are telling git that we want to commit the changes that we've staged with the `git add` command
* `-m`: this flag indicates that we will specify our commit message directly after that
* Finally in the quotes we've got our commit message, it is important to write short and descriptive commit messages

In our case we could set our commit message to something like `"Initial commit"` or `"Add README.md"` file for example.

If you don't specify the `-m` flag, Git will open the default text editor that we've configured in chapter 5 where you will be able to type the commit message directly.

After running the `git commit` command, we can use the `git status` command again to check the current status:

```
git status
```

Output:

```
On branch main
nothing to commit, working tree clean
```

As you can see, Git is telling us that there are no changes to be commited as we've already commited them.

Let's go ahead and make anothe change to the `README.md` file. You can open the file with your favourte text editor and make the change directly, or you can run the following command:

```
echo "Git is awesome!" >> README.md
```

The above would add a new line at the bottom of the `README.md` file. So if we were to run `git status` again we will see the following output:

```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

As you can see Git has detected that the `README.md` file has been modified and is also prompting us to use the command that we've learned to first stage/add the file!

In case that you wanted to change your last commit message, you can run the `git commit --amend` command. This will open the default editor where you can change your commit message. Also this allows you to change the commit changes.

The `git status` command gives us a great overview of the files that have changed, but it does not show us what actually the changes are. In the nect chapter we are going to learn how to check the differences from the last commit and the current changes.