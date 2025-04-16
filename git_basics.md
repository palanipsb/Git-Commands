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

```
## Git bisect

```sh

git bisect start        # Finds the commit that introduced a bug using binary search.
git bisect bad
git bisect good

```
## Git Tag

```sh

git tag <tag-name>                  # Creates, lists, or deletes tags for specific commits.
git tag -a <tag-name> -m "message"  # Creates, lists, or deletes tags for specific commits.

```
## Git archive

```sh

git archive --format=zip HEAD > repo.zip    # Creates an archive of the repository files.

```

## Git Submodules

```sh

git submodule add <repo-url>        # Manages submodules (nested repositories).
git submodule update

```

## Git worktree

```sh

git worktree add <path> <branch>    # Adds multiple working directories for the same repository.

```

## Aliases and Shortcuts 

```sh

git config --global alias.co checkout # Creates shortcuts for frequently used commands.
git config --gobal alias.br branch

```

## Debugging Commands 

```sh

git diff <commit-hash1> <commit-has2>   # Compares changes between different commits, branches, or working directories.
git diff main feature

git log --start                         # Shows commit history with a summary of changes for each commit.
git grep "search-string"                # Searches for a string or pattern in your repository.
git bisect run <script>                 # Automates git bisect using a script to test each commit.
git fsck                                # Verifies the integrity of the Git repository.
git log -S "search-term"                # Searches for commits where a string was added or removed. 
git show-branch                         # Displays the branch history in a compact form.
git rev-parse HEAD                      # Converts branch names or tags into commit hashes.
git whatchanged                         # Shows the file-level changes for each commit.

```

## Patch Management

```sh

git format-patch HEAD~3     # Generates patch files from commits.
git apply <patch-file>      # Applies a patch file to the working directory.
git am <patch-file>         # Applies patches and creates commits from them.
git diff --cached           # Shows the differences between the staging area and the last commit.
git reset HEAD <file>       # Unstages a file, moving it back to the working directory.

```

## Collaborative Workflow Commands

```sh

git push --force            # Force pushes changes to a remote branch (used cautiously).
git fetch --prune           # Cleans up deleted remote branches locally.
git pull --rebase           # Rebases instead of merging during a pull operation.
git remote prune origin     # Removes references to deleted remote branches. 
git cherry main feature     # Lists commits in the current branch that are not in the target branch.

```

## Rewriting History

```sh

git rebase --onto <new-base> <upstream> <branch>    # Rebases a range of commits onto a different branch.
git filter-branch --env-fiter '..'HEAD              # Rewrites commit history for advanced filtering.
git replace <commit-hash1> <commit-hash2>           # Replaces a commit with another. 
git reset --merge                                   # Resets the working directory and index, preserving uncommitted changes.
git commit --amend                                  # Modifies the most recent commit message or adds changes to it. 

```

## Advanced Commands

```sh

git reflog expire --all --expire=now    # Clears old or unnecessary reflog entries. 
git gc                                  # Cleans up unnecessary files and optimizes the repository. 
git worktree prune                      # Cleans up old worktree references.
git prune                               # Cleans up unreachable objects.
git is-tree HEAD                        # Displays the content of a tree object in Git.

```

## Security and Authentication

```sh

git credential approve              # Manages Git credentials. 
git config --list                   # Lists all configuration settings.
git verify-commit <commit-hash>     # Verifies signed commits. 

```

## Complete Categories Overview 

![alt text](<All category.png>)
![alt text](<All category 2.png>)