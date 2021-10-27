
# Git Rebase

Rebasing is often used as an alternative to merging. Rebasing a branch updates one branch with another by applying the commits of one branch on top of the commits of another branch. For example, if working on a feature branch that is out of date with a dev branch, rebasing the feature branch onto dev will allow all the new commits from dev to be included in feature. Here’s what this looks like visually:

### Visualization of the command :
![image](https://user-images.githubusercontent.com/54790525/138965417-52f36e80-fbd1-4eaa-8914-1a228988c4f4.png)
![image](https://user-images.githubusercontent.com/54790525/138965429-87265772-b89a-4a31-9deb-3a902d885540.png)


### Syntax : 
```bash
git rebase feature dev
```
where branch1 is the branch we want to rebase to the master.

### Difference between Merge and Rebase : 
Many people think that `Merge` and `Rebase` commands perform the same job but actually they are completely different and we will discuss this in the following lines.

-  #### Merge : 
  This command is used to integrate changes from some branch to another branch with keeping the merged branch at its base so you can easily return to earlier version of code if you want and the following picture show that : 
  ![Merge](https://i.imgur.com/jD4yhZ5.png)

### typical use of rebasing
#### Updating a Feature Branch
Lets say you’re working away on a feature branch, minding your own business.
![image](https://user-images.githubusercontent.com/54790525/138965621-337737eb-6758-4556-891b-54795a4735df.png)

Then you notice some new commits on dev that you’d like to have in your feature branch, since the new commits may affect how you implement the feature.

![image](https://user-images.githubusercontent.com/54790525/138965666-88f517f6-2906-4c7e-8937-e53404812c21.png)


You decide to run git rebase dev from your feature branch to get up-to-date with dev.
However when you run the rebase command, there are some conflicts between the changes you made on feature and the new commits on dev. Thankfully, the rebase process goes through each commit one at a time and so as soon as it notices a conflict on a commit, git will provide a message in the terminal outlining what files need to be resolved. Once you’ve resolved the conflict, you git add your changes to the commit and run git rebase --continue to continue the rebase process. If there are no more conflicts, you will have successfully rebased your feature branch onto dev.

![image](https://user-images.githubusercontent.com/54790525/138965979-f207053e-afcf-49a6-a392-fe4fd530011a.png)

Now you can continue working on your feature with the latest commits from dev included in feature and all is well again in the world. This process can repeat itself if the dev branch is updated with additional commits.

- #### Rebase :
  On the other hand `Rebase` command is used to transfer the base of the branch to be based at the last commit of the current branch which make them as one branch as shown in the picture at the top.
