# Git Cheat Sheet

## Cloning a repository
    git clone <url>
    
## Overwrite local commits
Download the latest without trying to merge or rebase anything:
```
git fetch --all
```
Reset the master branch to what you just fetched:
```
git reset --hard origin/master
```
The ```--hard``` option changes all the files in your working tree to
match the files in ```origin/master```.
