# Git basic comands

* git init + name to init a local repo
* git add, commit -m, push to add files to remote repo
* git push -u origin main to upload updated content (also to push branches)
* git remote add origin <host-or-remoteURL> to connect local and remote repo
* git checkout -b to create branch & switching. To push a remote branch, use git push origin -u <branchname>
* git checkout + branch name to switch
* create orphan (without content) branches: git checkout --orphan <branch> or git switch --orphan <branch>
* git merge to merge content from branches. Merging must be done in the branch that will receive the files. Type: git merge + branch name
* git pull -> Pulls remote data updated to local repo
* .gitignore to protect content
* remove things: rm [-f(optional, forces removal)] + file name. To remove branches locally, git branch -d + branch name. To remove remote branches, git push origin --delete + branch name
* git log: shows log



Best practice: delete branch once it's merged with the main branch.

# Rebase

Rebasing is the process of moving or combining a sequence of commits to a new base **commit**. (In contrast, merge deals with files)
![image.png](https://wac-cdn.atlassian.com/dam/jcr:4e576671-1b7f-43db-afb5-cf8db8df8e4a/01%20What%20is%20git%20rebase.svg?cdnVersion=1543)

Rebase shouldn't be performed on a shared feature branch (developed by multiple people).

Rebase is one of two Git utilities designed to integrate changes from one branch onto another. Rebasing is the process of combining or moving a sequence of commits on top of a new base commit. Git rebase is the linear process of merging.

It essentially unifies all the previous changes, not splitting the line in two. By putting branches in front, the previous commits aren't splitted, and makes everything cleaner.

Before rebase

```
 A---B---C topic
         /
    D---E---F---G master
```

After rebase
```
    A'--B'--C' topic
                 /
    D---E---F---G master
```
To use rebase, type git rebase + name of the branch (main, usually)

# Git stash

Git tiene un área llamada "stash" donde puedes almacenar temporalmente una captura de tus cambios sin enviarlos al repositorio. Está separada del directorio de trabajo (working directory), del área de preparación (staging area), o del repositorio.

* git stash para utilizarlo
* git apply para volver al área de trabajo
* git stash show para mostrarlos
* Cuando se usa un stash y para que no cause problemas, usar git stash clear.

# Git fetch vs git pull

* Git pull baja a local (y al área de trabajo) el contenido del repo, y además lo actualiza y une (hace un merge y un fetch a la vez) con lo que ya hay.
* Git fetch baja a local los cambios, pero sin integrarlo a lo que ya está en local.

# Revert to last commit

* git diff: shows changes. Names can be passed to select the file you want to see
* git checkout .: removes changes

# Revert a file to previous version

* revert a file to a previous version: the commit id is needed, to get that type git log (j up, k down, q quit, shift g all the way down). Then type git checkout <file id> -- name of the file

# Look at code in previous versions (does not revert, it lets you to see what the code looked like at a given time)

* Best practice: put the code to be examined in a different branch
* log changes and switch back to them

# revert entire projects to a previous version

* git reset --hard <id>

# Revert to a previous commit 

* Clone repo

```
git clone <repository-url>
```

* Change to that directory

```
cd <repository-name>
```

* Log the commits

```
git log --oneline
```

* Paste the commit

```
git checkout <commit-hash>
```

* Create a new branch and pass the commit

```
git checkout -b <new-branch-name> <commit-hash>
```

