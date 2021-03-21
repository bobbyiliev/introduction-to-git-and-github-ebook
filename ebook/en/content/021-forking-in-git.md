# Forking in Git

When contributing to an open-source project, you will not be able to make the changes directly to the project. Only the repository maintainers have that privilege.

What you need to do instead is to fork the specific repository, make the changes to the forked project and then submit a pull request to the original project. You will learn more about pull requests in the next chapters.

If you clone a repository that you don't have the access to and then try to push the changes directly to that repository, you would get the following error:

```
ERROR: Permission to laravel/laravel.git denied to bobbyiliev.
Fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

This is where Forks come into play!

In order to fork a repository, you need to visit the repository via your browser and click on the Fork button on the top right:

![Fork a repository](https://user-images.githubusercontent.com/21223421/111687243-bcab0900-8832-11eb-8e56-56ad301a473d.png)

Then choose the account that you want to fork the repository to:

![Choose an account to fork the repository under](https://user-images.githubusercontent.com/21223421/111687394-e6fcc680-8832-11eb-9ef1-707d40aca810.png)

Then it might take a few seconds for the repository to be forked under your account:

![Forking the repository](https://user-images.githubusercontent.com/21223421/111687619-22979080-8833-11eb-909d-1b66fe77ccda.png)

With that, you would have an exact copy of the repository in question under your account.

The benefit here is that you can now clone the forked repository under your account, make the changes to that repository as normal, and then once you are ready, you can submit a pull request to the original repository contributing your changes.

As we've now mentioned submitting pull requests a few times already, let's go ahead and learn more about pull requests in the next chapter!