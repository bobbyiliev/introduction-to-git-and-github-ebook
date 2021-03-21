# Pull Requests

You already know how to merge changes from one branch to another on your local Git repository.

To do the same thing on GitHub, you would need to open a Pull Request (or a Merge Request if you are using GitLab) or a PR for short and request a merge from your feature branch to the `main` branch.

The steps that you would need to take to open a Pull Request are:

* If you are working on an open-source project that you are not the maintainer of, first fork the repository as per chapter 21. Skip this step if you are the maintainer of the repository.
* Then clone the repository locally with the `git clone` command:

```bash
git clone git@github.com:your_user/your_repo
```

* Create a new branch with the `git checkout` command:

```bash
git checkout -b branch_name
```

* Make your code changes

* Stage the changes with `git add`

```bash
git add .
```

* And then commit them with `git commit`:

```bash
git commit -m "Commit Message"
```

* Then push your new branch to GitHub with `git push`:

```bash
git push origin branch_name
```

* After that, visit the repository on GitHub and click on the `Pull Requests` button and then click on the green `New pull request` button:

![Pull request](https://user-images.githubusercontent.com/21223421/111886569-409df600-89d7-11eb-87d5-88c935ef09b2.png)

* In there, choose the branch that you want to merge to and the branch that you want to merge from:

![Git Pull Request Compare](https://user-images.githubusercontent.com/21223421/111886583-675c2c80-89d7-11eb-8069-68a086dbc539.png)

* Then review the changes and add a title and description and hit the create button
* If you are working on a project with multiple contributors, make sure to select a few reviewers. Essentially reviewers are people who you would like to review your code before it gets merged to the `main` branch.

For a visual representation of the whole process, make sure to check out this step by step tutorial as well:

* [How to Submit Your First Pull Request on GitHub](https://www.digitalocean.com/community/tutorials/hacktoberfest-how-to-submit-your-first-pull-request-on-github)