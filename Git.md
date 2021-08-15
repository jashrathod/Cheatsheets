# Git Cheatsheet 

## Table of Contents

1. [Configure](#config)
2. [Setup & Init](#setup)
3. [Stage & Snapshot](#stage)
4. [Branch & Merge](#branch)
5. [Inspect & Compare](#inspect)
6. [Share & Update](#share)
7. [Tracking Path Changes](#track)
8. [Rewrite History](#history)

## <a name="config"></a>Configure

```sh
# Configure user information for all local repositories
git config --global user.name “[name]”
git config --global user.email “[valid-email]”
```

## <a name="setup"></a>Setup & Init

```sh
# Initialize an existing directory as a Git repository:
git init

# Retrieve an entire repository from a hosted location via URL:
git clone [url]
```

## <a name="stage"></a>Stage & Snapshot

```sh
# Show modified files in working directory, staged for your next commit:
git status

# Add a file as it looks now to your next commit (stage):
git add [file]

# Unstage a file while retaining the changes in working directory:
git reset [file]

# diff of what is changed but not staged:
git diff

# diff of what is staged but not yet committed:
git diff --staged

# Commit your staged content as a new commit snapshot:
git commit -m “[descriptive message]”
```

## <a name="branch"></a>Branch & Merge

```sh
# List your branches. a * will appear next to the currently active branch:
git branch

# Create a new branch at the current commit:
git branch [branch-name]

# Switch to another branch and check it out into your working directory:
git checkout

# Merge the specified branch’s history into the current one:
git merge [branch]

# Show all commits in the current branch’s history:
git log
```

## <a name="inspect"></a>Inspect & Compare

```sh
# Show the commit history for the currently active branch:
git log

# Show the commits on branchA that are not on branchB:
git log branchB..branchA

# Show the commits that changed file, even across renames:
git log --follow [file]

# Show the diff of what is in branchA that is not in branchB:
git diff branchB...branchA

# Show any object in Git in human-readable format:
git show [SHA]
```

## <a name="share"></a>Share & Update

```sh
# Add a git URL as an alias:
git remote add [alias] [url]

# Fetch down all the branches from that Git remote:
git fetch [alias]

# Merge a remote branch into your current branch to bring it up to date:
git merge [alias]/[branch]

# Transmit local branch commits to the remote repository branch:
git push [alias] [branch]

# Fetch and merge any commits from the tracking remote branch:
git pull
```

## <a name="track"></a>Tracking Path Changes

```sh
# Delete the file from project and stage the removal for commit:
git rm [file]

# Change an existing file path and stage the move:
git mv [existing-path] [new-path]

# Show all commit logs with indication of any paths that moved:
git log --stat -M
```

## <a name="history"></a>Rewrite History

```sh
# Apply any commits of current branch ahead of specified one:
git rebase [branch]

# Clear staging area, rewrite working tree from specified commit:
git reset --hard [commit]
```
