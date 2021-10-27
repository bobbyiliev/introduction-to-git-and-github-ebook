# Git Branches

So far, we have been working only on our Main branch, which is created by default when creating a new GitHub repository. In this chapter, you will learn more about Git Branches. Why you need them and how to work with them.

The official definition of a Git branch from the git-scm.com website is the following:

> A branch in Git is simply a lightweight movable pointer to one of these commits.

This might be a bit confusing in case that you are just getting started. So you could think of branches as a way to work on your project by adding a new feature of bug fixes without affecting the Main branch.

That way, each new feature or bug fix that you are developing could live on a separate branch, and later on, once you are ready and have fully tested the changes, you can merge the new branch to your main branch. You will learn more about merging in the next chapter!

If we look into the following illustration where we have a few branches, you can see that it looks like a tree, hence the term branching:

![Git Branches](https://user-images.githubusercontent.com/21223421/111696461-03056580-883d-11eb-82c4-7f8d926629e6.png)

Thanks to the multiple branches, you can have multiple people working on different features or fixes at the same time each one working on their own branch.

The image shows 3 branches:

* The main branch
* New Branch 1
* New Branch 2

The main branch is the default branch that you are already familiar with. We can consider the other two branches as two new features that are being developed. One developer could be working on a new contact form for your web application on branch #1, and another developer could be working on a user registration form feature on branch #2.

Thanks to the separate branches, both developers can work on the same project without getting into each others way.

Next, let's go ahead and learn how to create new branches and see this in action!

### Creating a new branch

Let's start by creating a new branch called `newFeature`. In order to create the branch, you could use the following command:

```bash
git branch newFeature
```

Now, in order to switch to that new branch, you would need to run the following command:

```bash
git checkout newFeature
```

> Note: You can use the `git checkout` command to switch between different branches.

The above two commands could be combined into 1, so that you don't have to create the branch first and then switch to the new branch. You could use this command instead, which would do both:

```bash
git checkout -b newFeature
```

Once you run this command, you will see the following output:

```
Switched to a new branch 'newFeature'
```

In order to check what branch you are currently on, you can use the following command:

```bash
git branch
```

Output:

```
  main
* newFeature
```

We can tell that we have 2 branches: the `main` one and the `newFeature` one that we just created. The star before the `newFeature` branch name indicates that we are currently on the `newFeature` branch.

If you were to use the `git checkout` command to switch to the `main` branch:

```bash
git checkout main
```

And then run `git branch` again. You will see the following output indicating that you are now on the `main` branch:

```
* main
  newFeature
```

### Making changes to the new branch

Now let's go ahead and make a change on the new feature branch. First switch to the branch with the `git checkout` command:

```bash
git checkout newFeature
```

> Note: we only need to add the `-b` argument when creating new branches

Check that you've actually switched to the correct branch:

```bash
git branch
```

Output:

```
  main
* newFeature
```

Now let's create a new file with some demo content. You can do that with the following command:

```bash
echo "<h1>My First Feature Branch</h1>" > feature1.html
```

The above will echo out the `<h1>My First Feature Branch</h1>` string and store it in a new file called `feature1.html`.

After that, stage the file and commit the change:

```bash
git add feature1.html
git commit -m "Add feature1.html"
```

The new `feature1.html` file will only be present on the `newFeature` branch. If you were to switch to the `main` branch and run the `ls` command or check the `git log`, you will be able to see that the file is not there.

You can check that by using the `git log` command:

```bash
git log
```

With that, we've used quite a bit of the commands that we've covered in the previous chapters!

### Compare branches

You can also compare two branches with the following commands.

* Shows the commits on `branchA` that are not on `branchB`:

```bash
git log BranchA..BranchB
```

* Shows the difference of what is in `branchA` but not in `branchB`:

```bash
git diff BranchB...BranchA
```

### Renaming a branch

In case that you've created a branch with the wrong name or if you think that the name could be improved as it is not descriptive enough, you can rename a branch by running the following command:

```bash
git branch -m wrong-branch-name correct-branch-name
```

If you want to rename your **current branch**, you could just run the following:

```bash
git branch -m my-branch-name
```

After that, if you run `git branch` again you will be able to see the correct branch name.

### Deleting a branch

If you wanted to completely delete a specific branch you could run the following command:

```bash
git branch -d name_of_the_branch
```

This would only delete the branch from your local repository, in case that you've already pushed the branch to GitHub, you can use the following command to delete the remote branch:

```bash
git push origin --delete name_of_the_branch
```

If you wanted to synchronize your local branches with the remote branches you could run the following command:

```bash
git fetch
```

### Conclusion

With that, our `newFeature` branch is now ahead of the main branch with 1 commit. So in order to get that new changes over to the main branch, we need to merge the `newFeature` branch into our `main` branch.

In the next chapter, you will learn how to merge your changes from one branch to another!

One thing that you might want to keep in mind is that in the past when creating a new GitHub repository the default branch name was called `master`. However, new repositories created on GitHub use `main` instead of `master` as the default branch name. This is part of GitHub's effort to remove unnecessary references to slavery and replace them with more inclusive terms.
