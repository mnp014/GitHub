# Delete all branches in local.

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
 
 # Delete all branches in Remote.
 (Make sure of origin and upstream before deleting. use `git remote -v` to check.)
 
 - Replace REMOTE_NAME with your remote name (e.g. origin)
 ```
 $ git branch -r | grep REMOTE_NAME/ | grep -v 'master$' | grep -v HEAD| cut -d/ -f2 | while read line; do git push REMOTE_NAME :$line; done;
 ```

 - Example
 ```
 $ git branch -r | grep origin/ | grep -v 'master$' | grep -v HEAD| cut -d/ -f2 | while read line; do git push origin :$line; done;
```
 - There can be a slash in branch name, Replace `cut -d/ -f2` with `sed 's#^\s*REMOTE_NAME/##g'`. 
 ```
 $ git branch -r | grep REMOTE_NAME/ | grep -v 'master$' | grep -v HEAD| s#^\s*REMOTE_NAME/##g | while read line; do git push REMOTE_NAME :$line; done;
 ```
 or
 - This command does not work for branches with `/` in its name. To fix this, you need to replace `cut -d/ -f2` with `cut -d/ -f2-`
 ```
 git branch -r | grep REMOTE_NAME/ | grep -v 'master$' | grep -v HEAD| cut -d/ -f2- | while read line; do git push REMOTE_NAME :$line; done;
 ```
 
 
 # In MacOS, 
 - Use `sed -E "s/^[[:space:]]*REMOTE_NAME\///g"`, also git push command could be `git push REMOTE_NAME :heads/$line` in case of tags with same name.
```
 $ git branch -r | grep "${REMOTE_NAME}/" | grep -v 'master$' | grep -v HEAD | sed -E "s/^[[:space:]]*${REMOTE_NAME}\///g" | while read line; do git push $REMOTE_NAME :heads/$line; done;
```
