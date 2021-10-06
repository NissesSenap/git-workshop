# Workshop instructions

This workshop is created to go through setting up a basic development environment to work with git and markdown.
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

To get a quick overview of markdown look at this document ^^ and check on this link
[markdownguide.org](https://www.markdownguide.org/cheat-sheet/).

## Azure DevOps

- Setup a [ssh key](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops#set-up-ssh-key-authentication)
- Add the ssh key to your Azure DevOps [profile](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops#step-2--add-the-public-key-to-azure-devops-servicestfs)
- Clone your first [repository](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops#step-2--add-the-public-key-to-azure-devops-servicestfs).

## Git

Here are a few basic git commands that will get you started.

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

# Stage changes done in filename
git add filename

# Stage all known files
git add -u

# Check changes before commit
git diff

# Create change message using the -m, don't do this overall
# Instead use git commit to be able to add more information
git commit -m "Add healthz endpoint to API"

# Amend your changed to the last commit
git commit --amend

# Remove your latest commit
git reset HEAD~

# log
git log

# Show changes in last commit
git show

# Reset a file to the last commit
# aka remove all your none commited changes in this file.
git checkout -- puppet-modules/Puppetfile

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
