# Git Status

Whenever you make changes to your Git project, you would want to verify what has changed before making a commit or before pushing your changes to GitHub, for example.

To check the current status of your project, you can use the `git status` command. If you run the `git status` command in the same directory where you initialized your Git project from the last chapter, you will see the following output:

```
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

As this is a fresh new repository, there are no commits and no changes yet. So let's go ahead and create a `README.md` file with some generic content. We can run the following command to do so:

```bash
echo "# Demo Project" >> README.md
```

What this would do is to output the `# Demo Project` and store it in the `README.md` file.

If you run `git status` again, you will then see the following output:

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
nothing added to commit but untracked files present (use "git add" to track)
```

As you can see, Git is detecting that there is 1 new file that is not tracked at the moment called `README.md`, which we just created. And already, Git is prompting us to use the `git add` command to start tracking the file. We will learn more about the `git add` command in the next chapter!

We are going to be using the `git status` command throughout the next few chapters a lot! This is particularly helpful, especially when you've modified a lot of files and you want to check the current status and see all of the modified, updated, or deleted files.