# Git Stash

`git stash` temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on.

Stashing is handy if you need to quickly switch context and work on something else, but you're mid-way through a code change and aren't quite ready to commit. The command saves your local modifications away and reverts the working directory to match the `HEAD` commit.

The modifications stashed away by this command can be listed with `git stash list`, inspected with `git stash show`, and restored (potentially on top of a different commit) with `git stash apply`.

<h2> Stashing your work </h2>

```bash
git stash
```

The git stash command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy.

For example, consider a file named `index.html`, which has been modified since the last commit.

![git-stash-example](https://user-images.githubusercontent.com/42696800/136789285-ca33c54c-7f58-465a-a6c8-49d2d541a422.png)

Note that by stashing all the local changes, the file has been restored to the version found in the most previous commit.

By default, running git stash will stash:

-   changes that have been added to your index (staged changes)
-   changes made to files that are currently tracked by Git (unstaged changes)

But it will not stash:

-   new files in your working copy that have not yet been staged
-   files that have been ignored

In case you want to stash the **untracked files** as well, then consider **adding the -u option** (or --include-untracked) tells git stash to also stash your untracked files.

You can include changes to **ignored files** as well by **passing the -a option** (or --all) when running git stash.

The following image shows the behaviour of git stash

![git-stash-options](https://user-images.githubusercontent.com/42696800/136792711-c0fabb73-8083-4c8a-b66d-1689037b5e3c.png)

<h2>Re-applying your stashed changes</h2>

```bash
git stash apply
```

You reapply the changes to your working copy and keep them in your stash with `git stash apply`. Alternatively, we can also use the `git stash pop` command. Popping your stash removes the changes from your stash and reapplies them to your working copy.

Consider the following example:

![git-stash-apply](https://user-images.githubusercontent.com/42696800/136791882-c43f5805-354c-47f1-8866-959d519a932e.png)

This covers the most popular use case for the git stash command.

You can check out [this resource](https://www.atlassian.com/git/tutorials/saving-changes/git-stash) to take a look at some more advanced use cases.

To see the official documentation for the command, you can go through this [git-scm page](https://git-scm.com/docs/git-stash).
