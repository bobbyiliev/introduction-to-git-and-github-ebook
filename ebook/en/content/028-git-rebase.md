
# Git Rebase

Rebasing is often used as an alternative to merging. Rebasing a branch updates one branch with another by applying the commits of one branch on top of the commits of another branch. For example, if working on a feature branch that is out of date with a dev branch, rebasing the feature branch onto dev will allow all the new commits from dev to be included in feature. Here’s what this looks like visually:

### Visualization of the command :
![image](https://user-images.githubusercontent.com/54790525/138965417-52f36e80-fbd1-4eaa-8914-1a228988c4f4.png)
![image](https://user-images.githubusercontent.com/54790525/138965429-87265772-b89a-4a31-9deb-3a902d885540.png)


### Syntax : 
```bash
git rebase feature dev
```
where branch1 is the branch we want to rebase to the master.

### Difference between Merge and Rebase : 
Many people think that `Merge` and `Rebase` commands perform the same job but actually they are completely different and we will discuss this in the following lines.

-  #### Merge : 
  This command is used to integrate changes from some branch to another branch with keeping the merged branch at its base so you can easily return to earlier version of code if you want and the following picture show that : 
  ![Merge](https://i.imgur.com/jD4yhZ5.png)

### typical use of rebasing
#### Updating a Feature Branch
Lets say you’re working away on a feature branch, minding your own business.
![image](https://user-images.githubusercontent.com/54790525/138965621-337737eb-6758-4556-891b-54795a4735df.png)

Then you notice some new commits on dev that you’d like to have in your feature branch, since the new commits may affect how you implement the feature.

![image](https://user-images.githubusercontent.com/54790525/138965666-88f517f6-2906-4c7e-8937-e53404812c21.png)


You decide to run git rebase dev from your feature branch to get up-to-date with dev.
However when you run the rebase command, there are some conflicts between the changes you made on feature and the new commits on dev. Thankfully, the rebase process goes through each commit one at a time and so as soon as it notices a conflict on a commit, git will provide a message in the terminal outlining what files need to be resolved. Once you’ve resolved the conflict, you git add your changes to the commit and run git rebase --continue to continue the rebase process. If there are no more conflicts, you will have successfully rebased your feature branch onto dev.

![image](https://user-images.githubusercontent.com/54790525/138965979-f207053e-afcf-49a6-a392-fe4fd530011a.png)

Now you can continue working on your feature with the latest commits from dev included in feature and all is well again in the world. This process can repeat itself if the dev branch is updated with additional commits.

- #### Rebase :
  On the other hand `Rebase` command is used to transfer the base of the branch to be based at the last commit of the current branch which make them as one branch as shown in the picture at the top.

### Rebasing interactively :

You can also rebase a branche on another `interactively`. This means that you will be prompted for options.
The basic command looks like this:

```bash
git rebase -i feature main
```

This will open your favorite editor (probably `vi` or `vscode`).

Let's create an example:

```bash
git switch main
git checkout -b feature-interactive
echo "<p>Rebasing interactively is super cool</p>" >> feature1.html
git commit -am "Commit to test Interactive Rebase"
echo "<p>With interactive rebasing you can do really cool stuff</p>" >> feature1.html
git commit -am "Commit to test Interactive Rebase"
```

So you are now on the `feature-interactive` branch with a commit on this branch that doesn't exist on the `main` branch, and there is a new commit on the `main` that is not in your branch.

Now using the interactive rebase commande:

```bash
git rebase -i main
```

Your favorite editor (`vi` like here or `vscode` if you've set it up correctly) should be open with something like this:

```
pick a21b178 Commit to test Interactive Rebase
pick cd3400c Commit to test Interactive Rebase

# Rebase 1d152d4..a21b178 onto 1d152d4
#
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

As you can see here, the first lines are the commits you made in this `feature-interactive` branche. Then, the remaining of the file is the help message.
If you look at this help message closely, you will notice that there are plenty of options. To use them all you need to do is to prefix the commit line you want to work on by the name of the command or its shortcut letter.

The basic command is `pick`, meaning that the current rebase will use these two commits to do its work.

In our case, if you want to update the commit message of the second commit, you would update this file like this (we just show the first lines as the remaining are not updates):

```
pick a21b178 Commit to test Interactive Rebase
r cd3400c Commit to test Interactive Rebase

# Rebase 1d152d4..a21b178 onto 1d152d4
#
...
```

Then you would save the file, as it is `vi` here, you would hit the key `:` and type `wq`. You should now see another file opened in the same editor, where you can edit your commit message, then save the file and that's it.

You can look at the result with the following command:

```bash
git log
```

Now that you now the basics on how to use this command, take a look at the help message. There are some usefull commend in there. My favorites are the `reword`, `fixup` and `drop` but feel free to experiment by yourself.