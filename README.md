# git-commands

This README provides useful git commands.

Git Resources:
* [Documentation](https://git-scm.com/docs)
* [Setup ssh key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
* [Commands (1)](https://training.github.com/downloads/github-git-cheat-sheet/)
* [Commands (2)](https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html)
* [Markdown (1)](https://www.markdownguide.org/cheat-sheet/)
* [Markdown (2)](https://guides.github.com/features/mastering-markdown/)

## General

Show current git configuration.
```
git config --list
```

Show current status.
```
git status
```

Show commit history.
```
git log
```

## Remote

Clone a repository.
```
git clone <remote_url>
```

Initialize a repository.
```
git init
```

Check current remotes.
```
git remote -v
```

Add remote.
```
git remote add <remote_name> <remote_url>
```

Remove remote.
```
git remote rm <remote_name>
```

Fetch changes.
```
git fetch -p <remote_name>
```
Example for the remote "origin".
```
git fetch -p origin
```

Merge changes into current branch.
```
git merge <branch_name>
```
Example for the remote "origin" and the branch "master". 
```
git merge origin/master
```
Example for local branch "dev".
```
git merge dev
```

Fetch and merge changes in one step.
```
git pull <remote_name> <branch_name>
```
Example for the remote "origin" and the branch "master". 
```
git pull origin master
```

Push changes to remote.
```
git push <remote_name> <branch_name>
```
Example for remote "origin" and branch "master".
```
git push origin master
```

## Branches

Check current branches.
```
git branch -v
```

Create and move to a new branch.
```
git checkout -b <new_branch_name>
```

Move to an existing branch.
```
git checkout <existing_branch_name>
```

Delete branch.
```
git branch -d <existing_branch_name>
```

## Changes

Show changes between branches.
```
git diff <base_branch> <updated_branch>
```

Show changes on current branch.
```
git diff
```

Show changes to a file.
```
git diff <file_name>
```

Undo changes to file. WARNING: resets file to last committed version.
```
git checkout -- <file_name>
```

Add file.
```
git add <path_to_file>
```

Add directory and all contents.
```
git add <path_to_directory>
```

Add all contents of current directory, including subdirectories.
```
git add .
```

Commit changes after adding files.
```
git commit -m "Describe changes in this commit message."
```

Add and commit changes to all tracked files in one step.
```
git commit -am "Describe changes in this commit message."
```

