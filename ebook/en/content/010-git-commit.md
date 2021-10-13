# Git Commit

Once you have added/staged your files, the next step is actually to commit the changes. So if you run `git status` again, you will be able to see that Git tells us that there are changes to be committed:

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

In this case, it is only the `README.md` file that will be committed. So in order to do so, we can run the following command:

```bash
git commit -m "Your Commit Message Here"
```

Rundown of the command:

* `git commit`: here, we are telling git that we want to commit the changes that we've staged with the `git add` command
* `-m`: this flag indicates that we will specify our commit message directly after that
* Finally, in the quotes we've got our commit message, it is important to write short and descriptive commit messages

In our case we could set our commit message to something like `"Initial commit"` or `"Add README.md"` file, for example.

If you don't specify the `-m` flag, Git will open the default text editor that we've configured in chapter 5 where you will be able to type the commit message directly.

Committing directly without staging files:

If you have not already staged your changes using `git add` command you can still directly commit all your changes using the following command.
```
git commit -a -m "Your Commit Message Here"
```
The `-a` flag here will automatically stage all the changes and commit them.

## Signing Commits
Git allows you to sign your commits. Commits signed with a verified signature in GitHub and GitLab display a verified label as shown below.
![GitHub Signed Commits](https://imgur.com/OvY20rM.png)
![GitLab Signed Commit](https://i.imgur.com/u5Oait2.png)

To sign commits, first you need to:
* make sure that you have GNU GPG installed on your host.
* Generate a GPG signing key pair if you don't already have
  ```bash 
  gpg --full-generate-key
  ```
* Use the `gpg --list-secret-keys --keyid-format=long` command to list the long form of the GPG keys
```bash
gpg --list-secret-keys --keyid-format=long
/Users/bobby/.gnupg/pubring.kbx
---------------------------------
sec   rsa4096/E630A0A00CAA7AAA 2021-10-01 [SC] [expires: 2026-10-01]
      5F1F417F8A043C8888888888E630F6D35CFA7ECD
uid                 [ultimate] Bobby Illiev (For signing git commits) <bobby@bobbyiliev.com>
ssb   rsa4096/46EE4AA180001AA6 2021-10-01 [E] [expires: 2026-10-01]
```
* Copy the long form of the GPG key ID you'd like to use. In this sample, the GPG key ID is `E630A0A00CAA7AAA`.
* Export the public key:
```bash
gpg --armor --export E630A0A00CAA7AAA
```
* Copy your GPG key, beginning with `-----BEGIN PGP PUBLIC KEY BLOCK-----` and ending with `-----END PGP PUBLIC KEY BLOCK-----`.
* Login to GitHub or GitLab and add a new GPG key under settings:
![GitHub Settings](https://i.imgur.com/k64wxvW.png)
![GitHub Add GPG Key page](https://i.imgur.com/sMeVvUN.png)
* Set your GPG signing key in Git: (If you intend to add the signing key per repository, the omit the `--global` flag)
```bash
git config --global user.signingkey E630A0A00CAA7AAA
```
* Enable automatic signing for all commits:
```bash
git config --global commit.gpgsign true
```
* Or Sign per commit by passing `-S` option to `git commit`:
```bash
git commit -S -m "your commit message"
```

After running the `git commit` command, we can use the `git status` command again to check the current status:

```bash
git status
```

Output:

```
On branch main
nothing to commit, working tree clean
```

As you can see, Git is telling us that there are no changes to be committed as we've already committed them.

Let's go ahead and make another change to the `README.md` file. You can open the file with your favorite text editor and make the change directly, or you can run the following command:

```bash
echo "Git is awesome!" >> README.md
```

The above would add a new line at the bottom of the `README.md` file. So if we were to run `git status` again, we will see the following output:

```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

As you can see, Git has detected that the `README.md` file has been modified and is also prompting us to use the command that we've learned to first stage/add the file!

In case that you wanted to change your last commit message, you can run the `git commit --amend` command. This will open the default editor where you can change your commit message. Also, this allows you to change the commit changes.

The `git status` command gives us a great overview of the files that have changed, but it does not show us what the changes actually are. In the next chapter, we are going to learn how to check the differences between the last commit and the current changes.

To check for commits that changed particular file you can use the `--follow` flag:

```bash
git log --follow [file]
```

The above shows the commits that changed the file, even across renames. 
