# Git basic comands

* git init + name to init a local repo
* git add, commit -m, push to add files to remote repo
* git push -u origin main to upload updated content
* git checkout -b to create branch & switching
* git checkout + branch name to switch
* git merge to merge content from branches. Merging must be done in the branch that will receive the files. Type: git merge + branch name
* git pull -> Pulls remote data updated to local repo

.gitignore to protect content

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