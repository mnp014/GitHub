# How to update Forked repo with the Original repo:
_____________________________________________________________________________________________
## Step1:
- Add the remote, call it "upstream":
```
    $ git remote add upstream https://github.com/whoever/whatever.git
```
--------------------------------------------------------------------------------------------
## Step2:
- Fetch all the branches of that remote into remote-tracking branches,
 such as upstream/master:
```
    $ git fetch upstream
```
--------------------------------------------------------------------------------------------
## Step3:
- Make sure that you're on your master branch:
```
    $ git checkout master
```
--------------------------------------------------------------------------------------------
## Step4:
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
_____________________________________________________________________________________________    