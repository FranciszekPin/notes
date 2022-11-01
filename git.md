# Git cheat sheet

## Dictionary

| term name       | description                                              |
| --------------- | -------------------------------------------------------- |
| index           | staging area                                             |
| HEAD            | pointer to the local branch you’re currently on          |
| fast-forward    | situation when merging branch is ahead of current branch |
| tracking branch | local branch with connection to remote branch -          |
|                 | doing `pull`/`push` will modify upstream pointer         |
| upstream branch | remote branch that is tracked by tracking branch         |

## Recording changes to repo

### Printing status

short version

```
git status -s
```

### Viewing changes

changed, but not staged (working tree - staging area)

```
git diff
```

staged will be included in commit (staging area - last commit)

```
git diff --staged
```

### Commiting

commit, viewing file changes

```
git commit -v
```

commit, including files not staged

```
git commit -a
```

### Removing files

firstly, remove file, then remove from git

```
rm <file> && git rm <file>
```

remove from staging area, but keep on disk

```
git rm --cached <file>
```

### Moving files

rename file

```
git mv <file1> <file2>
```

but it's equivalent to

```
mv <file1> <file2>
git rm <file1>
git add <file2>
```

## Viewwing commit history

show differences introduced in each commit

```
git log -p
```

show three last commits

```
git log -2
```

show info about each file

```
git log --stat
```

change output format (for example only one line per commit)

```
git log --pretty=oneline
```

specify own printing format (useful when scripting)

```
git log --pretty=format:"%h - %an, %ar : %s"
ca82a6d - Scott Chacon, 15 years ago : changed the verison number
085bb3b - Scott Chacon, 15 years ago : removed unnecessary test code
a11bef0 - Scott Chacon, 15 years ago : first commit
```

more info: `git help log` -> PRETTY FORMATS

show graph

```
git log --pretty=oneline --graph
```

show info about specific branch

```
git log <branch>
```

show info about all branches

```
git log --all
```

show info about commit

```
git show <commit>
```

### Limiting log output

Commits *after* some time

```
git log --since=2.weeks
```

Commits *before* some time

```
git log --until="2 years 1 day 3 minutes ago"
```

grep on commit messages

```
git log --pretty=oneline --grep="first"
```

grep on author

```
git log --author="Scott"
```

print only commits which changed occurance of specified string
(for example added or removed reference of some function)

```
git log -S function_name
```

limits commits to some subdir/file of repo (use as last option)

```
git log -- path/to/dir/or/file
```

exclude merges

```
git log --no-merges
```

## Undoing things

Modify last commit

```
git commit --amend
```

Move staged files to not staged/not tracked

```
git restore --staged <file>
```

Undo changes made to file

```
git restore <file>
```

Revert changes from specified commit by creating another commit

```
git revert <commit>
```

Move branch backward (reset changes)

```
git reset <commit>
```

[More about `git reset`](https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified)

## Working with remotes

List remote handles

```
git remote -v
```

Add remote

```
git remote add <shortname> <url>
```

Fetch changes from remote repo

```
git fetch <remote>
```

Fetch changes and merge from remote repo
(works only if branch is tracking remote branch)

```
git pull
```

Push branch `<branch>` to `<remote>`

```
git push <remote> <branch>
```

Show info about remote

```
git remote show <remote>
```

Rename remote

```
git remote rename <oldname> <newname>
```

Remove remote

```
git remote remove <remote>
```

## Git branching

Create branch

```
git branch <branch>
```

Change branch (there is also `git switch`)

```
git checkout <branch>
```

Create branch and checkout to it

```
git checkout -b <branch>
```

Remove branch

```
git branch -d <branch>
```

### Branch management

See last commit on each branch

```
git branch -v
```

See ALL branches (including remote)

```
git branch --all
```

See branches already merged to current branch (can be removed safely)

```
git branch --merged
```

The same, but relaive to specified branch

```
git branch --merged <branch>
```

Rename branch

```
git branch --move bad-branch-name corrected-branch-name
```

Add remote branch

```
git push --set-upstream origin branch-name
```

Delete remote branch

```
git push origin --delete bad-branch-name
```

### Remote branching

Get data from some remote

```
git fetch <remote>
```

Get data from all remotes

```
git fetch --all
```

Pushing (if remotebranch doesn't exists, creates it)

```
git push <remote> localbranch:remotebranch
```

Often shorter version can be used, if remote branch have same name

```
git push <remote> <branch>
```

#### Tracking branches

Create tracking branch for remote branch

```
git checkout -b <branch> <remote>/<branch>
```

Shorthand for this, tracking branch will have name same as upstream

```
git checkout --track <remote>/<branch>
```

Shorthand for shorthand, woking only if local branch
(a) doesn’t exist and (b) exactly matches a name on only one remote

```
git checkout <branch>
```

Change upstream of *existing* branch

```
git branch -u <remote>/<branch>
```

List tracking branches

```
git fetch --all; git branch -vv
```

Remove remote branch

```
git push <remote> --delete <branch>
```

### Rebasing

Applay work on another branch

```
git checkout <branch1>
git rebase <branch2>
git checkout <branch2>
git merge <branch1>
```

Take the client branch, figure out the patches since it diverged
from the server branch, and replay these patches in the client
branch as if it was based directly off the master branch instead.

```
git rebase --onto master server client
```

Rebase `<topicbranch>` onto `<basebranch>`

```
git rebase <basebranch> <topicbranch>
```

Rebase interactively

```
git rebase -i <commit>
```

## Moving work around

Move branch

```
git branch -f <branch> <commit>
```

Choose previous commits and apply them to current branch

```
git cherry-pick <Commit1> <Commit2> <...>
```

## Revision selection

### Ancestry References

Move to parent

```
git checkout HEAD^
```

Move to grandfather

```
git checkout HEAD~2
```

Chose parent branch to move

```
git checkout HEAD^2
```

### Commit Ranges

All commits reachable from `experiment` that aren’t reachable from `master`.

```
git log master..experiment
```

Commits in your current branch that aren’t in the master branch on your origin remote.

```
git log origin/master..HEAD
```

All commits that are reachable from refA or refB but not from refC (equivalent queries).

```
git log refA refB ^refC
git log refA refB --not refC
```

Master or experiment but not any common commits.

```
git log master...experiment
```

### Interactive adding

Run interactive tool

```
git add -i
```

### Stashing and cleaning

Put dirty state on stash stack

```
git stash [push] -u
```

List stashes

```
git stash list
```

```
git stash pop --index
```

### Searching through code base

```
git grep <pattern> <tree>
```

### Rewriting history

[check this link](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
