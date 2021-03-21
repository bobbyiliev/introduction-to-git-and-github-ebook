# Reverting changes

As with everything, there are multiple ways to do a specific thing. But what I would usually do in this case I want to undo my latest commit and then commit my new changes is the following.

* Let's say that you made some changes and you committed the changes:

```command
git commit -m "Committing the wrong changes"
```

* After that if you run `git log`, you will see the history of everything that has been committed to a repository.

* To undo the last commit, just run the following:

```command
git reset --soft HEAD~1
```

The above command will reset back with 1 point.

**Note:** the above would undo your commit, but it would keep your code changes if you would like to get rid of the changes as well, you need to do a hard reset: `git reset --hard HEAD~1`

* After that, make your new changes

* Once you are done with the changes, run `git add` to add any of the files that you would like to be included in the next commit:

```
git add .
```

* Then use `git commit` as normal to commit your new changes:

```
git commit -m "Your new commit message"
```

* After that, you could again check your history by running:

```
git log
```

Here's a screenshot of the process:

![Git How to undo latest commit digitalocean](https://i.imgur.com/L5zOGG1.png)

Another approach would be to use `git revert COMMIT_ID` instead.

Here is a quick video demo on how to do the above:

[Reverting changes](https://www.youtube.com/watch?v=54Hy6KnfbuY)