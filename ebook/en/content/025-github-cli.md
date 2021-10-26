# GitHub CLI

The GitHub CLI or `gh` is basically GitHub on command-line. 

You can interact with your GitHub account directly through your command line and manage things like pull requests, issues, and other GitHub actions.

In this tutorial, I will give a quick overview of how to install `gh` and how to use it!

## GitHub CLI Installation

As I will be using Ubuntu, to install `gh` you need to run the following commands:

```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key C99B11DEB97541F0
sudo apt-add-repository https://cli.github.com/packages
sudo apt update
sudo apt install gh
```

If you are on a Mac, you can install `gh` using Homebrew:

```bash
brew install gh
```

For any other operating systems, I recommend following the steps from the official documentation [here](https://github.com/cli/cli#installation).

Once you have `gh` installed, you can verify that it works with the following command:

```bash
gh --version
```

This would output the `gh` version:

```
gh version 1.0.0 (2020-09-16)
https://github.com/cli/cli/releases/tag/v1.0.0
```

In my case, I'm running the latest `gh` v1.0.0, which got released just a couple of days ago.

## Authentication

Once you have `gh` installed, you need to login to your GitHub account.

To do so, you need to run the following command:

```bash
gh auth login
```

You will see the following output:

```
? What account do you want to log into?  [Use arrows to move, type to filter]
> GitHub.com
  GitHub Enterprise Server
```

You have an option to choose between GitHub.com or GitHub Enterprise. Click enter and then follow the authentication process.

Another useful command is the `gh help` command. This will give you a list with the available `gh` commands that you could use:

```
USAGE
  gh <command> <subcommand> [flags]

CORE COMMANDS
  gist:       Create gists
  issue:      Manage issues
  pr:         Manage pull requests
  release:    Manage GitHub releases
  repo:       Create, clone, fork, and view repositories

ADDITIONAL COMMANDS
  alias:      Create command shortcuts
  api:        Make an authenticated GitHub API request
  auth:       Login, logout, and refresh your authentication
  completion: Generate shell completion scripts
  config:     Manage configuration for gh
  help:       Help about any command

FLAGS
  --help      Show help for command
  --version   Show gh version

EXAMPLES
  $ gh issue create
  $ gh repo clone cli/cli
  $ gh pr checkout 321

ENVIRONMENT VARIABLES
  See 'gh help environment' for the list of supported environment variables.

LEARN MORE
  Use 'gh <command> <subcommand> --help' for more information about a command.
  Read the manual at https://cli.github.com/manual

FEEDBACK
  Open an issue using 'gh issue create -R cli/cli'
```

Then let's clone an existing project which we will use to play with. As an example, we can use the [LaraSail](https://github.com/thedevdojo/larasail) repository. Rather than cloning the repository using the standard `git clone` command, we will use `gh` to do so:

```bash
gh repo clone thedevdojo/larasail
```

You will see the following output:

```
Cloning into 'larasail'...
```

After that `cd` into that folder:

```bash
cd larasail
```

We are now ready to move to some of the more useful `gh` commands!

## Useful GitHub CLI commands

Using `gh`, you can pretty much get all of the information for your repository on GitHub without having even to leave your terminal.

Here's a list of some useful commands:

### Working with GitHub issues

To list all open issues, run:

```bash
gh issue list
```

The output that you will see is:

```
Showing 4 of 4 open issues in thedevdojo/larasail

#25  Add option to automatically create database                                                  (enhancement)  about 3 months ago
#22  Remove PHP mcrypt as it is no longer needed                                                                 about 3 months ago
#11  Add redis support                                                                                           about 8 months ago
#10  Wondering about the security of storing root MySQL password in /etc/.larasail/tmp/mysqlpass                 about 3 months ago
```

You can even create a new issue with the following command:

```bash
gh issue create --label bug
```

Or if you wanted to view an existing issue, you could just run:

```bash
gh issue view '#25'
```

This would return all of the information for that specific issue number:

```
Add option to automatically create a database
Open • bobbyiliev opened about 3 months ago • 0 comments

Labels: enhancement


  Add an option to automatically create a new database, a database user and
  possibly update the database details in the .env file for a specific project



View this issue on GitHub: https://github.com/thedevdojo/larasail/issues/25
```

### Working with your GitHub repository

You can use the `gh repo` command to create, clone, or view an existing repository:

```bash
gh repo create
gh repo clone cli/cli
gh repo view --web
```

For example, if we ran the `gh repo view`, we would see the same README information for our repository directly in our terminal.

### Working with Pull requests

You can use the `gh pr` command with a set of arguments to fully manage your pull requests.

Some of the available options are:

```
  checkout:   Check out a pull request in git
  checks:     Show CI status for a single pull request
  close:      Close a pull request
  create:     Create a pull request
  diff:       View changes in a pull request
  list:       List and filter pull requests in this repository
  merge:      Merge a pull request
  ready:      Mark a pull request as ready for review
  reopen:     Reopen a pull request
  review:     Add a review to a pull request
  status:     Show status of relevant pull requests
  view:       View a pull request
```

With the above commands, you are ready to execute some of the main GitHub actions you would typically take directly in your terminal!

### Conclusion

Now you know what the GitHub CLI tool is and how to use it! For more information, I would recommend checking out the official documentation here:

[https://cli.github.com/manual/](https://cli.github.com/manual/)

I'm a big fan of all command-line tools! They can make your life easier and automate a lot of the daily repetitive tasks!

Initially posted here:
[What is GitHub CLI and how to get started](https://devdojo.com/bobbyiliev/what-is-github-cli-and-how-to-get-started)