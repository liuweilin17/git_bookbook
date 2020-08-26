* Show config

```
git config -l
git config --global -l
git config --local -l
```

* Commit template

``` 
vim .git-commit-template
 ```
Edit as following:
```
#### Subject Line ####
[PROJECT TAG/BUG FIX] Refactor/Remove/Fix

#### Body ####
Why?
How?
SIM:
CR:
Wiki:
TT:
```
Set config:
```
git config --global commit.template ~/.git-commit-template
```
