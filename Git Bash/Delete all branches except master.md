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
