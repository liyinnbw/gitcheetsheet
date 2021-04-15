# gitcheetsheet

## Commit
Add & commit
```
git commit -am "message"
```

Pretty print commit history of current branch (hash - author, time : message)
```
git log --pretty=format:"%h - %an, %ar : %s"
```

Rever last remote commit (this will create a new commit, good for team work)
```
git checkout remote-branch
git pull
git revert HEAD
git push
```

Revert last N commits (this will create a new commit, good for team work)
```
git checkout remote-branch
git pull
git revert --no-commit HEAD~N..
git commit -am "message"
git push
```

## Branch Mangement
List local branches
```
git branch
```

List remote branches
```
git branch -r
```

List local+remote branches
```
git branch -a
```

List local branch with time
```
git for-each-ref --sort=committerdate refs/heads/ --format='%(committerdate:short) %(refname:short)'
```

Create & checkout local branch
```
git checkout -b new-branch-name
```

Switch to another branch already in local repo
```
git checkout branch-name
```

Switch to another branch at remote [more info](https://stackoverflow.com/questions/1783405/how-do-i-check-out-a-remote-git-branch)
```
git fetch
git checkout branch-name
```

Rename a branch locally
```
git branch -m new-branch-name
```

Rename a branch locally & remotely
```
git branch -m new-branch-name
git push origin -u new-branch-name
git push origin --delete old-branch-name
```

Delete a local branch
```
git branch -d local-branch-name
```

## Merge
Merge a remote branch to local branch
```
git fetch
git checkout local-branch-name
git merge origin/remote-branch-name

or 

git checkout remote-branch-name
git pull
git checkout local-branch-name
git merge remote-branch-name
```

Merge a local branch to remote branch
```
git fetch
git checkout remote-branch-name
git merge local-branch-name
```

## Resolve Merge Conflicts
Accept a local file in full
```
git checkout --ours PATH/FILE
```

Accept a remote file in full
```
git checkout --theirs PATH/FILE
```

Accept all local files in full
```
grep -lr '<<<<<<<' . | xargs git checkout --ours
```

Accept all remote files in full
```
grep -lr '<<<<<<<' . | xargs git checkout --theirs
```

## Multiple Remotes
Add another remote
```
git remote add <remote-name> <url>
```

View all remotes
```
git remote -v
```

Pull from a remote branch
```
git pull <remote-name> <branch-name>
```

Push to a remote branch
```
git push <remote-name> <branch-name>
```

### Good Readings:

https://missing.csail.mit.edu/2020/version-control/
