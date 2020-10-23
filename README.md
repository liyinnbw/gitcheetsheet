# gitcheetsheet

## Commit
Add & commit
> git commit -am "message"

## Branch Mangement
Create & checkout local branch
> git checkout -b new-branch-name

## Resolve Merge Conflicts
Accept a local file in full
> git checkout --ours PATH/FILE

Accept a remote file in full
> git checkout --theirs PATH/FILE

Accept all local files in full
> grep -lr '<<<<<<<' . | xargs git checkout --ours

Accept all remote files in full
> grep -lr '<<<<<<<' . | xargs git checkout --theirs
