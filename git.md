
<hr>
<p align="center">
    <img alt="Git" src="./img/git-logo.png" height="104" width="250">
</p>
<hr>

- [git terms](#git-terms)
- [git commit](#git-commit)
- [git branch](#git-branch)
- [git reset](#git-reset)
- [git status](#git-status)
- [git checkout](#git-checkout)
- [git revert](#git-revert)
- [git merge](#git-merge)
- [git stash](#git-stash)
- [git remote](#git-remote)
- [git log](#git-log)
- [git diff](#git-diff)
- [git rebase](#git-rebase)
- [git misc](#git-misc)
- [undo some changes from prev commit](#undo-some-changes-from-prev-commit)
- [gitignore examples](#gitignore-examples)
- [Workflows](#workflows)

## git terms

Keys | Description
:--|:--
working directory | holds actual files
index | staging area, performed by git add
head | points to last commit

## git commit

Keys | Description
:--|:--
--amend |
--amend -C HEAD | keep commit msg
--amend --no-edit | keep commit msg

## git branch

Keys | Description
:--|:--
--all |
-r | shows all remote branches
--merged | branches already merged into current branch
--no-merged | all branches that contain work you haven't merged in)
-vv | shows tracking branches
-a | shows all remote & local
issue2 df273d | create branch from commit
-d -r origin/dev | delete only remote tracking branch
git fetch --all; git branch --v | shows updated information
-b remotebranch origin/remotebranch

## git reset

> resets index to last commit

Keys | Description
:--|:--
unstages |
HEAD \<file> | unstage, less danger -> stash & branch
checkout -- \<file> | Less danger -> stash & branch
--hard HEAD^ | reset all tracked files to match most recent commit
alias unstage | reset HEAD --
git reset \<file> |
--soft HEAD^ |
git reset HEAD~2 |
git reset 'HEAD@{1}' | undo reset


## git status

Keys | Description
:--|:--
-s | short format

## git checkout

Keys | Description
:--|:--
-- \<file> | blows away all changes
-b newbranch 7g5b3r |

## git revert
> reverts specified commit by adding new commit to tip, so it's reversible

Keys | Description
:--|:--
revert <commit you want to undo> |
git reset --hard HEAD^ | to reverse revert

## git merge
> 3-way merge will create new commit from two commits, thus they will share history

Keys | Description
:--|:--
git merge master feature |
no-ff \<branch> | force a merge commit when git would normally do a ff merge

## git stash

Keys | Description
:--|:--
save [message] | stash with message
save -u | stash untracked files
list | list stashes
apply [name] | apply stash with [name]
pop [stash] | deletes stash from stack after applied
branch <name> [stash] | create a branch with <name> from [stash]
drop |
clear | delete all stashes
list --stat |
show stash@{0} |
show stash@{2} --patch |
--keep-index | only unstaged

## git remote

Keys | Description
:--|:--
show origin | shows remote branches
remote -v |
prune origin | clean up deleted remote branches
git push origin :todelete | delete remote branch


## git log

Keys | Description
:--|:--
pretty |
--oneline -p |
--graph |
-g --oneline |
--shortstat | changed/inserted/del
--stat | abbreviated stats
-p | show patch introduced
-p -2 | difference in each of last 2


## git diff
> shows diff between working tree & idx

Keys | Description
:--|:--
git diff HEAD |
HEAD~5 |
4f3b…3xc9 |
git diff | changed, not staged
--cached/--staged | shows diff between index and last commit
--staged | staged, will commit
--word-diff | changed words, not whitespace

## git rebase

> rewind/apply/apply

Keys | Description
:--|:--
git rebase master |
git rebase -i --root master | rebase from initial commit to HEAD
git rebase -i master pic/squash/edit/fixup |
--continue/abort |

## git misc

Keys | Description
:--|:--
add -p (patch) |
clean -f | removes/deletes all untracked
squash |
reflog |
filter-branch --tree-filter 'rm -f passwords.txt' HEAD | removes all instances of password.txt
clean |
apply |
cherry-pick |
show-ref | shows where head is
update-ref |
ls-files |
tag |
bisect |
blame |

## undo some changes from prev commit

Keys | Description
:--|:--
git revert -n <commit> | stops short of commiting reversion
git reset |
git add -p |
git commit |
git checkout . |

## gitignore examples

pattern | Description
:--|:--
*.o | ignore all files with o extension
libraries/ | ignore any directories named libraries
/libraries/ | ignore libraries directory in same directory as .gitignore

## Workflows

> Example workflows

|Centralized|
:--|
|1. git init --bare
|2. git clone
|3. git push/pull
|4. if conflict -> git pull --rebase origin master


|Feature Branch|
:--|
|1. checkout -b branch
|2. changes/commit
|3. git push
|4. file pull request
|5. git checkout master
|6. git pull
|7. git pull origin branch
|8. git push
