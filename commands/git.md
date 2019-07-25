## Tutorial

* [Git 教學- Git 書- 為你自己學Git | 高見龍](https://gitbook.tw/)
* [Learn Git Branching](https://learngitbranching.js.org/)


## Usage
### could not read Username for 'https://github.com': terminal prompts disabled
* To enter username and password
```
$ env GIT_TERMINAL_PROMPT=1 go get github.com/examplesite/myprivaterepo
```

* or using ssh key
```
$ git config --global --add url."git@github.com:".insteadOf "https://github.com/"
```


### How to show changed file name only with git log?
```
$ git log --name-only 
```


### How to show changed file status with git log?
```
$ git log --name-status
```


### Remove a Big object (housekeeping)
1. find big objects

```
$ git verify-pack -v .git/objects/pack/pack-${SHA-1}.idx | sort -k 3 -n | tail -n 10
```

2. find the object what is

```
$ git rev-list --objects --all | grep ${SHA-1}
```

3. find the commit id which the file added

```
$ git log --pretty=oneline --branches -- ${File_name}
```

4. Delete the object (Rewrite the commit)

```
$ git filter-branch --index-filter \
   'git rm --cached --ignore-unmatch ${File_name}' -- commit_id^..
```

5. Remove reference and re-pack

```
$ rm -Rf .git/refs/original
$ rm -Rf .git/logs/
$ git gc
```


### How to revert a Git repository to a specific commit
```
$ git reflog # get commit_id which you want to revert
$ git reset --hard commit_id
```
