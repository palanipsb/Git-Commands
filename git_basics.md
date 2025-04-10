# Git
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

```