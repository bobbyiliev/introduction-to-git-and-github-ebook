# Git Log

In order to list all of the previous commits, you can use the following command:

```bash
git log
```

This will provide you with your commit history, the output would look like this:

```
commit da46ce39a3fd663ff802d013f834431d4b4159a5 (HEAD -> main)
Author: Bobby Iliev <bobby@bobbyiliev.com>
Date:   Fri Mar 12 17:14:02 2021 +0000

    Update README.md

commit fa583473b4be2807b45f35b755aa84ac78922259
Author: Bobby Iliev <bobby@bobbyiliev.com>
Date:   Fri Mar 12 17:01:17 2021 +0000

    Initial commit
```

The entries are listed, in order, from most recent to oldest.

Rundown of the output:

* `commit da46ce39a3fd663ff802d013f834431d4b4159a5`: Here you can see the specific commit ID
* `Author: Bobby Iliev... `: Then you can see who created the changes
* `Date:   Fri Mar 12...`: After that, you've got the exact time and date when the commit was created
* Finally, you have the commit message. This is one of the reasons why it is important to write short and descriptive commit messages so that later on, you could tell what changes were introduced by the particular commit.

If you want to check the differences between the current state of your repository and a particular commit, what you could do is use the `git diff` command followed by the commit ID:

```bash
git diff fa583473b4be2807b45f35b755aa84ac78922259
```

In my case the output will be the following:

```
diff --git a/README.md b/README.md
index 9366068..2b14655 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,2 @@
 # Demo Project
+Git is awesome
```

So the difference between that specific commit and the current state of the repository is the change in the `README.md` file.

In case that you wanted to see only the commit IDs and commit messages on one line, you could add the `--oneline` argument:

```bash
git log --oneline
```

Output:

```
* da46ce3 (HEAD -> main) Update README.md
* fa58347 Initial commit
```

With that, you now know how to check your commit history! Next, let's go ahead and learn how to exclude specific files from Git!