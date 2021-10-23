
# Git Alias

If there is a common but complex Git command that you type frequently, consider setting up a simple Git alias for it. Aliases enable more efficient workflows by requiring fewer keystrokes to execute a command. It is important to note that **there is no direct git alias command**. Aliases are created through the use of the git config command and the Git configuration files.

```bash
git config --global alias.co checkout
```

Now when I use the command git co, it is just as if I had typed that longer git checkout command.

```bash
git co -b branch1
```

Output

```bash
Switched to a new branch 'branch1'
```

Creating the aliases will not modify the source commands. So git checkout will still be available even though we now have the git co alias.

```bash
git checkout -b branch2
```

Output

```bash
Switched to a new branch 'branch2'
```

Aliases can also be used to wrap a sequence of Git commands into new Git command.
