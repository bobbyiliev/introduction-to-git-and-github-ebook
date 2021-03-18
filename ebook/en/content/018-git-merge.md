# Git Merge

Once the developers are ready with their changes, they can merge their feature branches into the main branch and make those features live on the website.

![Merge changes to main branch](https://user-images.githubusercontent.com/21223421/111697237-fd5c4f80-883d-11eb-9506-4347ba482250.png)

If you followed the steps from the previous chapter, then your `newFeature` branch is now ahead of the main branch with 1 commit. So in order to get that new changes over to the main branch we need to merge the `newFeature` branch into our `main` branch.

You can do that by following these steps:

* First switch to your `main` branch:

```
git checkout main
```

* After that in order to merge your `newFeature` branch and the changes that we created in the last chapter, run the following `git merge` command:

```
git merge newFeature
```

Output:

```
Updating ab1007b..a281d25
Fast-forward
 feature1.html | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature1.html
```

As you were on the `main` branch when you ran the `git merge` command, Git will take all of the commits from that branch and merge them into the `main` branch.

Now if you run the `ls` command you will be able to see the new `feature1.html` file and if you check the commit history with the `git log` command you will see the commit from the `newFeature` branch present on your `main` branch.

In this case the merge went through smoothly as there were no merge conflicts. However if you are working on a real project with multiple people making changes, there might be some merge conflicts. Essentially this happens when changes are made to the same line of a file, or when one developer edits a file on one branch and another developer deletes the same file.


TO DO

Resolving conflicts?