
# Git Rebase

This command aims to change the base of a certain branch to another base (usually used when we need to apply features to the master branch).

### Visualization of the command :
![Rebase](https://media.geeksforgeeks.org/wp-content/uploads/20200415234509/Rebasing-in-git.png)

### Syntax : 
```bash
git rebase master branch1
```
where branch1 is the branch we want to rebase to the master.

### Difference between Merge and Rebase : 
Many people think that `Merge` and `Rebase` commands perform the same job but actually they are completely different and we will discuss this in the following lines.

-  #### Merge : 
  This command is used to integrate changes from some branch to another branch with keeping the merged branch at its base so you can easily return to earlier version of code if you want and the following picture show that : 
  ![Rebase](https://media.geeksforgeeks.org/wp-content/uploads/20200416011501/Merging-in-git.png)

  - #### Rebase :
  On the other hand `Rebase` command is used to transfer the base of the branch to be based at the last commit of the current branch which make them as one branch as shown in the picture at the top.
