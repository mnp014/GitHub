# How to update Forked repo with the Original repo:
_____________________________________________________________________________________________
## Step 1:
- Add the remote, call it "upstream":
```
    $ git remote add upstream https://github.com/whoever/whatever.git
```
--------------------------------------------------------------------------------------------
## Step 2:
- Fetch all the branches of that remote into remote-tracking branches,
 such as upstream/master:
```
    $ git fetch upstream
```
--------------------------------------------------------------------------------------------
## Step 3:
- Make sure that you're on your master branch:
```
    $ git checkout master
```
--------------------------------------------------------------------------------------------
## Step 4:
- Rewrite your master branch so that any commits of yours that
 aren't already in upstream/master are replayed on top of that
 other branch:
```
    $ git rebase upstream/master
```
--------------------------------------------------------------------------------------------
## Step 5: (Optional)
- Push to view changed on my remote-forked-branch
```
    $ git push
```    
--------------------------------------------------------------------------------------------
## Step 6:
- Now the local master is even with remote master
- Now switch to the branch to be updated:
```
    $ git checkout <localBranch>
```
--------------------------------------------------------------------------------------------
## Step 7: 
- Pull changes from upstream's master to localBranch 
```
    $ git pull upstream master
```    
--------------------------------------------------------------------------------------------
## Step 8: (Optional)
- Push to view changed on my remote-forked-branch
```
    $ git push
```  
_____________________________________________________________________________________________    
