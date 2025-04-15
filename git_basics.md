# Git Commands - Basics
## Git history
    .git # this folder holds the folders and files and history

## Add code basic commands
```sh

git init                    # Initializes a new Git repository in the current directory.
git clone <repo-url>        # Creates a copy of an existing Git repository (remote or local)
git status                  # Shows the current state of the working directory and staging area. 
git add .                   # Stages changes (files) for the next commit.
git commit -m "message"     # Records changes to the repository. Use -m for a commit message. 
git log                     # Displays the commit history for the repository.
git log --oneline           # Displays the commit history for the repository in one line.   
git diff                    # Shows the difference between changes in the working directory and the repository.
git diff <commit-hash1>     # Shows the difference between changes to a specifc commit hash in the working directory and the repository.
git show <commit-hash>      #   Displays the changes introduced by a specific commit.
git config --global user.name "Your Name"       # Configures user details and preferences for Git.
git config --global user.email you@example.com  # Configures user details and preferences for Git.
git help <command>          # Displays help information for a Git command.

```
## Undoing Changes commands
```sh

git reset <commit hash>       # This will remove all the history on top from this commit id and moved to unstaging area.
git reset --soft HEAD~1     # Undo last commit, keep changes staged 
git reset --mixed HEAD~1    # Undo last commit, unstage changes 
git reset --hard HEAD~1     # Undo last commit and discard changes 

git revert <commit-hash>    # Creates a new commit to undo the changes of a previous commit.

git clean -f                # Remove untracked files 
git clean -fd               # Remove untracked files and directories

```

## Staging and Stashing Commands
```sh

git stash                   # Temporarily saves changes that are not ready to commit.
git stash pop               # Applies the most recent stash and removes it from the stash list.
git stash list              # Lists all stashes saved in the repository.
git stash drop stash@{n}    # Removes a specific stash entry.
git stash apply stash@{n}   # Applies a stash without removing it from the stash list.
git stash clear             # Removes a last stash entry.

```

## Collaboration Commands

```sh

git remote add <name> <url>     # Manages connections to remote repositories.
git remote remove <name>        # Manages connections to remote repositories.

git fetch                       # Downloads changes from a remote repository without applying them.
git pull                        # Fetches changes from a remote repository and merges them into the current branch.

git push origin <branch-name>   # Uploads local commits to a remote repository.
git clone                       # Clones a remote repository to your local machine.

```

## Branching Commands
    We shoud never commit to the main branch
    HEAD - All the changes we made will go to the HEAD poiter that poiting to a branch
    Fork - We can fork other's branch and do changes, so it will be ou copy and it wont affect other's branch and not allowed also.
    upstream - we add remote other's git URL to our local, which is upstream URL.
    pullrequest

```sh

git branch                      # List branches 
git branch <branch-name>        # Create a branch 
git branch -d <branch-name>     # Delete a branch

git checkout <branch-name>      # Switches to a branch.
git checkout <commit-hash>      # Switches to a specific commit.

git switch <branch-name>        # Switches branches (an alternative to git checkout).
git merge <branch-name>         # Combines changes from one branch into another.
git rebase <branch-name>        # Reapplies commits from one branch onto another, rewriting history.

```

## Viewing History

```sh

git reflog                      # Displays a log of all reference changes (branch and HEAD movements).
git blame <file-name>           # Shows who made changes to each line of a file.
git shortlog                    # Summarizes commit history by author.
git log --graph                 # Displays a visual representation of the commit history. 

```

## Cherry-Picking and Rebasing

```sh

git cherry-pick <commit-hash>       # Applies specific commits from one branch to another.
git rebase -i HEAD~3                # Squash, edit, or reorder commits during a rebase.