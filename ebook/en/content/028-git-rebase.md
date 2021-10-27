
# Git Rebase

This command aims to change the base of a  branch to another base (usually used when we need to apply features to the master branch).

### Visualization of the command :
![image](https://user-images.githubusercontent.com/54790525/138965417-52f36e80-fbd1-4eaa-8914-1a228988c4f4.png)
![image](https://user-images.githubusercontent.com/54790525/138965429-87265772-b89a-4a31-9deb-3a902d885540.png)


### Syntax : 
```bash
git rebase feature dev
```
where branch1 is the branch we want to rebase to the master.

### Difference between Merge and Rebase : 
Many people think that `Merge` and `Rebase` commands perform the same job. but actually, they are completely different and we will discuss this in the following lines.

-  #### Merge : 
  This command is used to integrate changes from some branch to another branch with keeping the merged branch at its base so you can easily return to the earlier version of code if you want and the following picture shows that : 
  ![Merge](https://i.imgur.com/jD4yhZ5.png)

  - #### Rebase :
  On the other hand `Rebase` command is used to transfer the base of the branch to be based at the last commit of the current branch, which makes them as one branch as shown in the picture at the top.
