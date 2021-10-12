# Git Diff

As mentioned in the last chapter, the `git status` command gives us a great overview of the files that have changed, but it does not show us what the changes actually are.

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

As we only changed the `README.md` file, Git is showing us the following:

* `diff --git a/README.md b/README.md`: here git indicates that it shows the changes made to the `README.md` file since the last commit compared to the current version of the file.
* `@@ -1 +1,2 @@`: here git indicates that 1 new line was added
* `+Git is awesome`: here, the important part is the `+`, which indicates that this is a new line that was added. In case that we remove a line, you would see a `-` sign instead.

In our case, as we only added 1 new line to the file, Git indicates that only 1 file was changed and that only 1 new line was added.

Next, let's go ahead and stage that change and commit it with the comments that we've learned from the previous chapters!

* Stage the changed file:

```bash
git add README.md
```

* Then again run `git status` to check the current status:

```bash
git status
```

The output would look like this, indicating that there is 1 modified file:

```
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
```

* Commit the changes:

```bash
git commit -m "Update README.md"
```

Finally, if you run `git status` again you will see that there are no changes to be committed.

I always run `git status` and `git diff` before making any commits, just so that I'm sure what has changed.

> Note 1 : `git diff --staged` will only show the changes to the file in "staged" area.

> Note 2 : `git diff HEAD` will show all changes to tracked files(file in last snapshot), if you have all the changes staged for commit then both the commands give same output.

In some cases, you would like to see a list of the previous commits. We will learn how to do that in the next chapter.