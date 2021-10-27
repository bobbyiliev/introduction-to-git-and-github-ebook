# Git Stash

`git stash` is a handy command that helps you in cases where you might need to stash away your local changes and reset your codebase to the most recent commit in order to work on a more urgent bug/feature.

In other words, this command allows you to revert your current working directory to match the `HEAD` commit while keeping all the local modifications safe.

Once you are ready to get back to working on the code you had stashed away, just restore them with a single command!

## Stashing Your Work

```bash
git stash
```

For example, consider a file named `index.html` which has been modified since the last commit.

![git-stash-example](https://user-images.githubusercontent.com/42696800/136789285-ca33c54c-7f58-465a-a6c8-49d2d541a422.png)

Notice that the running `git status` command says that there are no new changes once the `git stash` command is executed!

Here WIP stands for Work-In-Progress and these are used to index the various stashed copies of your work.

An important thing to keep in mind before stashing all new changes is that, by default, `git stash` **will not stash all the untracked and ignored files.** (Here, _untracked files_ are the files that weren't part of the last commit i.e, new files in your local repo)

In case you want to include these untracked files in the stash, you'll need to add the **-u** option.

```bash
git stash -u
```

Similarly, all the files in the `.gitignore` file (i.e, _the ignored files_) will also be excluded from your stash. But you can include them by using the **-a option**

```bash
git stash -a
```

The following illustrations depict the behaviour of the `git stash` command when the above two options are included:

![git-stash-options](https://user-images.githubusercontent.com/42696800/136953468-8bbcbc7e-54e3-4927-b3e7-9ebd96db0fe2.png)

## Restoring the Stashed Changes

```bash
git stash apply
```

This command is used to reapply all the local modifications done before that copy of the work was stashed.

Note that another command that can be used to achieve this is the `git stash pop` command. Here _popping_ refers to the process of removing the most recent stash content and reapplying them to your working copy.

The difference between these two commands is that the `git stash pop` command **will remove these particular changes from the stash** whereas the `git stash apply` command **will retain those changes in the stash** even after restoring them.

Consider the previous example itself, in which the file `index.html` was stashed. In the following image, you can see how restoring all those changes affects your local repo.

![git-stash-apply](https://user-images.githubusercontent.com/42696800/136791882-c43f5805-354c-47f1-8866-959d519a932e.png)

But what if you have multiple stashes and aren't sure which one you want to start working on? This is where the next command comes into the picture!

## Handling Multiple Stashed Copies of Your Work

Similar to the process involved in resetting the local repository to a particular commit, the first step involved in handling multiple stashes is to **take a look at the various stashes available**.

```bash
git stash list
```

This command shows an indexed list of all the available stashes along with a **message corresponding to their respective recent commits**.

Consider the following example wherein there are two available stashes. One, when a new script file was added and another when this script file was altered.

![git-stash-2](https://user-images.githubusercontent.com/42696800/136959951-cee9e074-7132-4b3b-82fb-9ac28c80cce7.png)

Note that the most recent stash is always indexed as 0.

Once you know which stash you want to restore to your local codebase, the command used to restore those modifications is:

```bash
git stash apply n
```

The alternative syntax used to achieve this is as follows:

```bash
git stash apply "stash@{n}"
```

Here **n** is the index of the stash you want to restore.
