# Tasks

If you install git for the fist time you will need to configure git

```shell
git config.email <email@example.com>
git config.user.name "First last name"
```

## part 1

- Create a new repository in your Azure DevOps project
- Create a small Markdown file containing some text data
- Create a branch
- Commit your changes
- Push the changes to your remote repository
- Create a [PR](https://docs.microsoft.com/en-us/azure/devops/repos/git/pull-requests?view=azure-devops)
- Ask a friend to review
  - Get a PR to review
  - If you think the PR looks okay approve it
- View the changes in Azure DevOps
- Checkout main branch
- Pull changes from remote

## part 2

- Check commit history/log
- Show the last changes locally
- Add a image to your Markdown file, follow a similar workflow as in part 1
  - Preview the Markdown file in your Markdown reader.
  - Commit the image
- Perform a change to the image,
  - git diff, what can you see?

## part 3 pipelines

- Create a Azure DevOps pipeline to trigger on PR:s
- For inspiration look at [azure-pipelines.yml](azure-pipelines.yml)
- How to setup a trigger at [PR](https://docs.microsoft.com/en-us/azure/devops/repos/git/branch-policies?view=azure-devops)
- Merge azure-pipelines.yml to main
- Edit some file and create a PR, see that the our pipeline auto triggers
  - Don't forget to actually create the PR and not just push to a branch

## Part 4 gitignore

- Create a .gitignore file containing a filename called hello.md
- create a file called hello.md
- What do you see when writing `git status`
