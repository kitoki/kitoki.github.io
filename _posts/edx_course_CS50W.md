title: CS50's web programming with python and javascript


## GIT

`git [command] -help`

> setup
```git
git config --list
git config --global -l
git config --global --unset name
git config --global user.name "Dammy Adams"
git config --global user.email "my-email@gmail.com"
```

> start a project
```git
git init <directory>
git clone <url>
```

> make a change
```git
git add <file>
git add .
git commit -m "commit message"
git commit -am "commit message"
git commit --amend
```

> basic concepts
```git
main: default development branch
origin: default upstream repo
HEAD: current branch
HEAD^: parent of HEAD
HEAD-4: great-great grandparent of HEAD
```

> branches
```git
git branch
git branch <new-branch>
git checkout <branch>
git checkout -
git checkout -b <new-branch>
git checkout -b <local-branch-name> -t <remote>/<branch>
git branch -d <branch>
git branch -D <branch>
git branch -m OldName NewName
git tag <tag-name>
git branches --no-merged
git branches --merged
```

> merging
```git
git checkout b
git merge a
git merge --squash a
```

> rebasing
```git
git checkout feature
git rebase main
git rebase -i main
git rebase 0i Head-3
```

> undoing things
```git
git mv <existing_path> <new_path>
git rm <file>
git rm --cached <file>
git checkout <commit_ID>
git revert <commit_ID>
git reset <commit_ID>

```

> review your repo
```git
git status
git log --oneline
git diff
git diff commit1_ID commit2_ID
```

> stashing
```git
git stash
git stash save "comment"
git stash -p
git stash list
git stash apply
git stash pop stash@{2}
git stash show stash@{1}
git stash drop stash@{1}
git stash clear
```

> synchronizing
```git
git remote add <alias> <url>
git remote
git remote remove <alias>
git remote rename <old> <new>
git fetch <alias>
git fetch <alias> <branch>
git pull
git pull --rebase <alias>
git push <alias>
git push <alias> <branch>
git push origin-delete remote-branch
```

> questions :
- git commit vs push




