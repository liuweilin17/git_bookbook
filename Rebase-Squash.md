#### Introduction
*  [rebase](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)
* [Rewrite history](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)

#### Example 1 

squash all the commit of your feature branch(a.k.a `speaker-recognition`) and create pull requests(a.k.a merge to `develop`) without conflicts with `develop`

* Method 1:

  We first rename current branch ```feature1-branch``` to ```feature1-branch-bak``` to back up our changes. 

  Then we create another new branch ```feature1-branch ``` from origin/develop, which are used to push to remote ```feature1-branch```

  Then we go to new branch ```feature1-branch```, merge and squash the commits of ```feature1-branch-bak``` into ```feature1-branch```. Notice, the text file contains all the commit message and we probably conclude them as one sentence.

  Finally, ```feature1-branch``` is ready to push to remote ```feature1-branch```. ```-f``` is needed since we are changing the history.

  In the following example, ```speaker-recognition``` corresponds to ```feature1-branch```.

  ```
  # fetch updates from remote branch you want to merge to
  git fetch origin develop
  
  # create new speaker-recognition from origin/develop
  git checkout -b speaker-recognition origin/develop --no-track
  
  # merge and squash speaker-recognition-bak to speaker-recognition
  git merge --squash speaker-recognition-bak
  
  # commit all the changes in speaker-recognition branch
  # use [git commit --amend] to change last commit message
  git commit -a
  
  # force push to remote speaker-recognition branch
  git push -f origin speaker-recognition
  ```

  

* Method 2

  This method is easier, but may fix more conflicts. If the updates on the remote branch is small, we could use that.

  ```
  # fetch the remote develop branch
  git fetch origin develop
  
  # rebase to origin develop
  # use [s] command to do the squash
  git rebase -i origin/develop
  
  # git rebase --continue ???
  
  git push -f origin speaker-recognition
  ```
  
