# Method 1: When you have *unpushed* commits:
- Use the **reflog** to find the first action before the rebase started.
- **reset --hard** back to it (to the first action).
```
    $ git reflog

    b4fdab3 HEAD@{0}: rebase: some commit
    2e41c2d HEAD@{1}: rebase: another commit
    a3e21ab HEAD@{2}: checkout: moving from master to my-branch
    ...

    $ git reset HEAD@{2} --hard
```
 - Now you should be back to before the rebase started.
  <br><br> [NOTE: To find the right place to reset to, you just pick the entry closest to top that doesn't start with "rebase".]
---
# Method 2: When you *don't* have *unpushed* commits:
- If the rebase is the only thing you have done on the branch, i.e. you have no unpushed commits/changes, then you could just delete the local branch with **git branch -D** and then check it out again:
```
    $ git checkout my-branch
    $ git rebase master
    // not happy with result
    $ git checkout master
    $ git branch -D my-branch
    $ git checkout my-branch
```     
OR
- You could also **reset --hard** to the origin branch:
```
$ git reset --hard origin/my-branch
```
