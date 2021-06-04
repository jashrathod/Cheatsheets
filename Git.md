# Git Cheatsheet 

## Table of Contents

1. [Configure](#config)
2. [Setup & Init](#setup)
3. [Stage & Snapshot](#stage)
4. [Branch & Merge](#branch)
5. [Inspect & Compare](#inspect)
6. [Share & Update](#share)
7. [Tracking Path Changes](#track)

## <a name="config"></a>Configure

Configure user information for all local repositories

```sh
git config --global user.name “[name]”
```
```sh
git config --global user.email “[valid-email]”
```

## <a name="setup"></a>Setup & Init

Initialize an existing directory as a Git repository:
```sh
git init
```
Retrieve an entire repository from a hosted location via URL:
```sh
git clone [url]
```

## <a name="stage"></a>Stage & Snapshot

Show modified files in working directory, staged for your next commit:
```sh
git status
```
Add a file as it looks now to your next commit (stage):
```sh
git add [file]
```
Unstage a file while retaining the changes in working directory:
```sh
git reset [file]
```
diff of what is changed but not staged:
```sh
git diff
```
diff of what is staged but not yet committed:
```sh
git diff --staged
```
Commit your staged content as a new commit snapshot:
```sh
git commit -m “[descriptive message]”
```

## <a name="branch"></a>Branch & Merge

List your branches. a * will appear next to the currently active branch:
```sh
git branch
```
Create a new branch at the current commit:
```sh
git branch [branch-name]
```
Switch to another branch and check it out into your working directory:
```sh
git checkout
```
Merge the specified branch’s history into the current one:
```sh
git merge [branch]
```
Show all commits in the current branch’s history:
```sh
git log
```

## <a name="inspect"></a>Inspect & Compare

Show the commit history for the currently active branch:
```sh
git log
```
Show the commits on branchA that are not on branchB:
```sh
git log branchB..branchA
```
Show the commits that changed file, even across renames:
```sh
git log --follow [file]
```
Show the diff of what is in branchA that is not in branchB:
```sh
git diff branchB...branchA
```
Show any object in Git in human-readable format:
```sh
git show [SHA]
```

## <a name="share"></a>Share & Update

Add a git URL as an alias:
```sh
git remote add [alias] [url]
```
Fetch down all the branches from that Git remote:
```sh
git fetch [alias]
```
Merge a remote branch into your current branch to bring it up to date:
```sh
git merge [alias]/[branch]
```
Transmit local branch commits to the remote repository branch:
```sh
git push [alias] [branch]
```
Fetch and merge any commits from the tracking remote branch:
```sh
git pull
```

## <a name="track"></a>Tracking Path Changes

Delete the file from project and stage the removal for commit:
```sh
git rm [file]
```
Change an existing file path and stage the move:
```sh
git mv [existing-path] [new-path]
```
Show all commit logs with indication of any paths that moved:
```sh
git log --stat -M
```

## Rewrite History

Apply any commits of current branch ahead of specified one:
```sh
git rebase [branch]
```
Clear staging area, rewrite working tree from specified commit:
```sh
git reset --hard [commit]
```
