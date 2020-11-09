* list

  ```shell
  git branch # list global branch
  git branch -r # list remote branch
  git branch -a # list all the branches name
  ```
  
* fetch

```shell
git fetch origin <branchname> # fetch a remote branch
git checkout <branchname> # create a corresponding local branch
```

* rename

```shell
git branch -m <oldname> <newname> # rename other branch
git branch -m <newname> # rename current branch
```

* create

```shell
git checkout -b <newname> # create a branch from the default branch
git checkout -b <newname> <existname> # create a branch from an existing branch
```

* delete

```
git branch -d <deleteBranch>
```

* checkout a file from another branch

```
git checkout <othername> -- filename.js
```

