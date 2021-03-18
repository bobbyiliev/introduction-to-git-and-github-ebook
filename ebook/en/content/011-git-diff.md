# Git Diff

As mentioned int he last chapter the `git status` command gives us a great overview of the files that have changed, but it does not show us what actually the changes are.

You can check the actual changes that were made with the `git diff` command. If we were to run the command in our repository, we would see the following output:

```
diff --git a/README.md b/README.md
index 9366068..2b14655 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,2 @@
 # Demo Project
+Git is awesome
```

As we only changed the `README.md` file, Git is shpowing us the following:

* `diff --git a/README.md b/README.md`: here git indicates that it is showing the changes made to the `README.md` file since the last commit compared to the current version of the file.
* `@@ -1 +1,2 @@`: here git indicates that 1 new line was added
* `+Git is awesome`: here the important part is the `+` which indicates that this is a new line that was added, in case that we remove a line you would see a `-` sign instead.

In our case, as we only added 1 new line to the file, Git indicates that only 1 file was changed and that only 1 new line was added.

Next let's go ahead and stage that change and commit it with the commants that we've lerned from the previous chapters!

* Stage the changed file:

```
git add README.md
```

* Then again run `git status` to check the current status:

```
git status
```

The output would look like this indicating that there is 1 modified file:

```
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
```

* Commit the changes:

```
git commit -m "Update README.md"
```

Finally if you run `git status` again you will see that there are no changes ot be commited.

I aways run `git status` and `git diff` before making any commits, just so that I'm sure what has changed.

In some cases you would like to see a list of the previous commits, we will learn how to do that in the next chapter.