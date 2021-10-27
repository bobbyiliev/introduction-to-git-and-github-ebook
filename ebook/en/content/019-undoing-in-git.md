# Reverting changes

As with everything, there are multiple ways to do a specific thing. But what I would usually do in this case I want to undo my latest commit and then commit my new changes is the following.

* Let's say that you made some changes and you committed the changes:

```bash
git commit -m "Committing the wrong changes"
```

* After that if you run `git log`, you will see the history of everything that has been committed to a repository.

* Unfortunately, after you commit the wrong changes, you realize that you forget to add files to the commit or forget to add a small change to committed files.

* To solve that all you need to do is make these changes and stage them by running` git add` then you can `amend` the last commit by running the following command:

```bash
git commit --amend
```

**Note:** The above command will also let you change the commit message if you need.


## Resetting Changes (⚠️ Resetting Is Dangerous ⚠️) 

> You need to be careful with resetting commands because this command will erase commits from the repository and delete it from the history.

Example:
```bash
git reset --soft HEAD~1
```

The above command will reset back with 1 point.

**Note:** the above would undo your commit, but it would keep your code changes if you would like to get rid of the changes as well, you need to do a hard reset: `git reset --hard HEAD~1`

Syntax:
```bash
git reset [--soft|--hard] [<reference-to-commit>]
```

* After that, make your new changes

* Once you are done with the changes, run `git add` to add any of the files that you would like to be included in the next commit:

```bash
git add .
```

* Then use `git commit` as normal to commit your new changes:

```bash
git commit -m "Your new commit message"
```

* After that, you could again check your history by running:

```bash
git log
```

Here's a screenshot of the process:

![Git How to undo latest commit digitalocean](https://i.imgur.com/L5zOGG1.png)

**Note:** You can reset your changes by more than one commit by using the following syntax:
```bash
git reset --soft HEAD~n
```
where `n` is the number of commits you want to reset back.

Another approach would be to use `git revert COMMIT_ID` instead.

Here is a quick video demo on how to do the above:

[Reverting changes](https://www.youtube.com/watch?v=54Hy6KnfbuY)
