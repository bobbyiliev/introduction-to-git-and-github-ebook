# Git Pull

If you are working on a project with multiple people, the chances are that the codebase will change very often. So you would need to have a way to get the latest changes from the GitHub repository to your local machine. 

You already know that you can use the `git push` command to push your latest commits, so to do the opposite and pull the latest commits from GitHub to your local project, you need to use the `git pull` command.

To test this, let's go ahead and make a change directly on GitHub directly. Once you are there, click on the `README.md` file and then click on the pencil icon to edit the file:

![Edit File GitHub](https://user-images.githubusercontent.com/21223421/111460030-2688bd00-8724-11eb-9569-d6327847b443.png)

Make a minor change to the file, add a descriptive commit message and click on the `Commit Changes` button:

![Commit change via GitHub](https://user-images.githubusercontent.com/21223421/111460194-5afc7900-8724-11eb-9c43-a8952961fca8.png)

With that, you've now made a commit directly on GitHub, so your local repository will be behind the remote GitHub repository.

If you were to try and push a change now to that same branch, it would fail with the following error:

```
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'git@github.com:bobbyiliev/demo-repo.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

As stated in the output, the remote repository is ahead of your local one, so you need to run the `git pull` command to get the latest changes:

```bash
git pull origin main
```

The output that you will get will look like this:

```
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 646 bytes | 646.00 KiB/s, done.
From github.com:bobbyiliev/demo-repo
 * branch            main       -> FETCH_HEAD
   da46ce3..442afa5  main       -> origin/main

 README.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

We can see that the `README.md` file was changed and that there were 2 new lines added and 1 line deleted.

Now, if you were to run `git log`, you will see the commit that you've made on GitHub available locally.

Of course, this is a simplified scenario. In the real world, you would not make any changes directly to GitHub, but you would most likely work with other people on the same project, and you would have to pull their latest changes regularly.

You need to make sure that you pull the latest changes every time before you try to push your changes.

Now that you know the basic Git commands let's go ahead and learn what Git Branches are.