# Workshop instructions

This workshop is created to go through setting up a basic development environment to work with git and Markdown.
It's mostly created for windows users and it's focused on Azure DevOps but with adoptions it should work just fine with GitHub or
other providers for that matter.

## Tasks

Before checking out the tasks read through the rest of the README,
when you are ready jump in to [TASKS.md](TASKS.md)

## Vscode

The first step of developing is to have a good development environment (this is where DevOps comes in).

A good basic tool that is well used is  [vscode](https://code.visualstudio.com/download).

Vscode supports extensions and have a good marketplace to make the available.

- [Markdown linting](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [Azure Pipelines](https://marketplace.visualstudio.com/items?itemName=ms-azure-devops.azure-pipelines)
- [PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)
- [Spell checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

## Markdown

To get a quick overview of Markdown look at this document ^^ and check on this link
[markdownguide.org](https://www.markdownguide.org/cheat-sheet/).

## Azure DevOps getting started

- Setup a [ssh key](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops#set-up-ssh-key-authentication)
- Add the ssh key to your Azure DevOps [profile](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops#step-2--add-the-public-key-to-azure-devops-servicestfs)
- Clone your first [repository](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops#step-2--add-the-public-key-to-azure-devops-servicestfs).

## Git

For a good visualization of [git](https://marklodato.github.io/visual-git-guide/index-en.html).

If you want your commands more compacted you can find a few basic commands bellow.

```shell
# status in your local repo
git status

# Rebase
git pull --rebase

# create a new branch and jump in to it
git checkout -b branch1

# Go in to a existing branch
git checkout branch1

# List local branches
git branch -v

# Check changes before commit
git diff

# Stage changes done in filename
git add filename

# Stage all known files
git add -u

# Check changes before commit on staged files
git diff --cached

# Create change message using the -m, don't do this overall
# Instead use git commit to be able to add more information
git commit -m "Add healthz endpoint to API"

# Amend your changed to the last commit
git commit --amend

# Push to remote repository
git push

# Remove your latest commit
git reset HEAD~

# log
git log
git log --graph --decorate --stat

# Show changes in last commit
git show

# Restore a file to the last commit
# aka remove all your none commited changes in this file.
git restore puppet-modules/Puppetfile

# Show remote repositories
git remote -v
```

### Commit messages

Writing good commit messages is a art that takes a long time to learn but in the long run you
will thank your self if you do it [right](https://chris.beams.io/posts/git-commit/).

## Gitignore

.gitignore is a way to ignore specific files/folders that you might create locally.
For example a normal file to ignore is a .env file where you would store all your development variables.

When creating a new repository you will get asked if you want to create a language specific .gitignore file,
but if you forget this you can always create one after.

To generate a good basic gitignore file that is language specific
you can use [gitignore.io](gitignore.io).

## Azure DevOps pipelines

Sadly Azure DevOps don't auto create pipelines from the pipelines files that you have created in your repo.
Instead you have to [manually](https://stackoverflow.com/questions/59067096/create-a-new-pipeline-from-existing-yml-file-in-the-repository-azure-pipelines) create them.

Azure DevOps PR validation is rather different from how GitHub manages it.
Instead of writing yaml to say what happens on a PR,
you have to create a [branch policy](https://docs.microsoft.com/en-us/azure/devops/repos/git/branch-policies?view=azure-devops)
to tell the pipeline to run.

## GUI

If you don't feel comfortable using the cli (Command Line Interface) there are multiple GUI (Graphical User Interfaces) to manage source code.

One solution that have been gaining traction is to use [vscode](https://code.visualstudio.com/) to both program and mange git.
If you want to go this route I recommend that you add the [gitlens extension](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) to vscode.

To install it from vscode push `ctrl + p` and write the following.

```vscode
# gitlens
ext install eamodio.gitlens
```

### vscode usage

Before changing anything it mostly good to create a branch.

![branch](/resources/branch.png)
You are now ready to edit your files.

In the picture below you can see that I have modified the content of a file and it hasn't been staged and thus not ready to be commited.
This is the ecvivialent of `git status`

![modified](/resources/modified.png)

Push the + sign and next to to the `M` to stage the file.

This will make your file staged.
You are now ready to commit your change.
This is the ecvivialent of `git add README.md`

![staged](/resources/staged.png)

So lets write our first commit message.
This is the ecvivialent of `git commit -m "My first commit"`

![commit](/resources/commit.png)

To push your code to your remote repository you can do.
This is the ecvivialent of `git push`

![push](/resources/push.png)

Now you should be able to view your pushed code in your remote location.
