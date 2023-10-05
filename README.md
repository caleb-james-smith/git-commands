# git-commands

This README provides useful git commands and links for additional information.

Resources:
* [Git Documentation](https://git-scm.com/docs)
* [Git Tutorial](https://kbroman.org/github_tutorial)
* [Git Commands (1)](https://training.github.com/downloads/github-git-cheat-sheet/)
* [Git Commands (2)](https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html)
* [Setup SSH Key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
* [Markdown Syntax (1)](https://www.markdownguide.org/cheat-sheet/)
* [Markdown Syntax (2)](https://guides.github.com/features/mastering-markdown/)
* [Markdown Editor (1)](https://stackedit.io/)
* [Markdown Editor (2)](https://dillinger.io/)
* [Markdown Editor (3)](https://markdown-it.github.io/)

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

Fetch changes (latest branches, tags, etc.):
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

## Merge

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
If there are merge conflicts, use
```
git status
```
to see which files have conflicts.
You can edit and save these files, choosing what you want the final version to be.
After editing and saving these files, you can add them and then commit the changes to finish the merge.
```
git add <file_name_1>
git add <file_name_2>
git add <file_name_3>
git commit -m "Fixed merge conflicts"
```
If there are merge conflicts and you want to abort the merge, you can use this command.
```
git merge --abort
```
This will restore the branch to the state before the merge.

## Branches

Check current branches.
```
git branch -v
```

Other ways to show the current branch.
```
git rev-parse --abbrev-ref HEAD
git branch --show-current
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

## Commits

Show the current commit.
```
git rev-parse HEAD
git rev-parse --short HEAD
```

## Tags

List current tags.
```
git tag
```

Create a new tag.
```
git tag <new_tag_name>
```

Create a new tag and include a description.
```
git tag <new_tag_name> -a "Describe this tag."
```

Checkout an existing tag.
```
git checkout <existing_tag_name>
```

Push a single tag to remote.
```
git push origin <existing_tag_name>
```

Push all tags to remote.
```
git push origin --tags
```

## Changes

Show changes to a file.
```
git diff <file_name>
```

Show changes on current branch.
```
git diff
```

Show changes between branches.
```
git diff <base_branch> <updated_branch>
```

Show changes between two commits.
```
git diff <old_commit> <new_commit>
```

Undo local changes to a file.
WARNING: resets a file to the last committed version. Uncommitted work will be lost.
```
git checkout -- <file_name>
```

Undo local changes to all files.
WARNING: resets all files to the last committed versions. Uncommitted work will be lost.
```
git reset --hard
```

Undo last commit (soft version).
Using --soft maintains the changes as uncommitted local modifications.
```
git reset --soft HEAD~1
```
Then you may unstage changes if you like.
```
git reset HEAD <file_name>
```
Then you may discard the unstaged changes if you like.
WARNING: this removes these changes.
```
git checkout -- <file_name>
```

Note: "git restore" commands only work for git versions 2.23+ .
```
git restore --staged <file_name>
git restore <file_name>
```

Undo last commit (hard version).
Using --hard does not keep the changes from the last commit.
WARNING: removes changes from latest commit and returns to state before latest changes and commit.
```
git reset --hard HEAD~1
```
Force push reverted state to remote (run after git reset to revert commit locally).
WARNING: removes latest commit from remote.
```
git push origin +HEAD
```

Add file.
```
git add <file_name>
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

Change most recent commit message. 
```
git commit --amend -m "New commit message"
```

Force push to remote branch.
This is required after changing commit message if the commit was already pushed to the remote branch.
```
git push <remote> <branch> -f
```

