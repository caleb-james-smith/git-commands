# git-commands

This README provides useful git commands and links for additional information.

Git Resources:
* [Documentation](https://git-scm.com/docs)
* [Tutorial](https://kbroman.org/github_tutorial)
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
git add <path_to_file_1>
git add <path_to_file_2>
git add <path_to_file_3>
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

Push a single tag to remote.
```
git push origin <existing_tag_name>
```

Push all tags to remote.
```
git push origin --tags
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

