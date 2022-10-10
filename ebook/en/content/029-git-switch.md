# Git Switch

`git switch` is not a new feature but an additional command to switch/change branch feature which is already available in the overloaded git checkout command. That's why, pretty recently, the Git community decided to publish a new command: `git switch`. As the name implies.

### Syntax : 

```bash
git switch <branch-name>
```

### Visualization of the command:

![git-switch-branch-](https://user-images.githubusercontent.com/55313215/193835157-2981b00b-6b6a-41a2-b34b-37d1bbd89a77.png)

### Difference between Switch and Checkout:

As you can see, its usage is very straightforward and similar to "git checkout". But the huge advantage over the "checkout" command is that "switch" does NOT have a million other meanings and capabilities.

As it is quite a new member of the Git command family, you should check if your Git installation already includes it.

### Switch Back and Forth Between Two Branches

In some scenarios, it might be necessary for you to switch back and forth between two branches repeatedly. Instead of always writing out the branch names in full, you can simply use the following shortcut:

### Syntax : 

```bash
git switch -
```

Using the dash character as its only parameter, the "git switch" command will check out the previously active branch. As said, this can come in very handy if you have to go back and forth between two branches a bunch of times.
