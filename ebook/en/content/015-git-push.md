# Git Push

Then finally once you've made all of your changes, you've staged them with the `git add .` command and then you committed the changes with the `git commit` command, you have to push those changes to your remote GitHub repository.

Before you can push to your remote GitHub repository, you would need to fisrt create your remote repository via GitHub as per Chapter 6.

Once you have your remote GitHub repository ready, you can add it to your local project with the following command:

```
git remote add origin git@github.com:your_username/your_repo_name.git
```

> Note: Make sure to change the `your_username` and `your_repo_name` details accordingly.

This is how you would link your local Git project with your remote GitHub repository.

If you've read the previous chapter, you will most likely notice we are using SSH as the authentication method.

If you did not follow the steps from the previous chapter, you can use HTTPS rather than SSH:

```
git remote add origin https://github.com/your_username/your_repo_name.git
```

To do so just use the `git push` command:

```
git push origin main
```

If you are using SSH with your SSH key uploaded to GitHub, the push command will not ask you for a password but it would push your changes to GitHub straight away.

In case that you did not run the `git remote add` command you will get the following error:

```
fatal: 'origin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

This would mean that you've not added your GitHub repository as the remote repository. This is why we run the `git remote add` command in order to create that connection between your local repository and the remote GitHub repository.

Note that the connection would be in place if you used the `git clone` command to clone an existing repository from GitHub to your local machine. We will go through the `git pull` command in the next few chapters as well.

After running the `git push` command, you can head over to your GitHub project and you will be able to see the commits that you've made locally, present on GitHub. If you were to click on the `commits` link, you will be able to see all commits just as if you were to run the `git log` command:

![GitHub commits](https://user-images.githubusercontent.com/21223421/111459731-c1cd6280-8723-11eb-996f-5982879f811b.png)

Now that you now how to push your latest changes from your local Git project to your GitHub repository, it's time to learn how to pull the latest changes from GitHub to your local project.