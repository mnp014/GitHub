 - Delete all branches except master and develop.md
```
git branch | grep -v "master" | xargs git branch -D 
```
 - Delete all branches except master and develop.md
```
git branch | grep -v "master\|develop" | xargs git branch -D
```
 - For an easier reuse you could also alias this useful snippet.
```
alias gbr="git branch | grep -v "master" | xargs git branch -D"
```
 - If you have branches containing master then use.
 ```
 git branch | grep -ve " master$" | xargs git branch -D
 ```
or
 ```
 ack -v "\s+master"
 ```
