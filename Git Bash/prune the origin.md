#### Remove information on branches that were deleted on origin:
##### When branches get deleted on origin, your local repository won't take notice of that. You'll still have your locally cached versions of those branches (which is actually good) but git branch -a will still list them as remote branches.

You can clean up that information locally like this:
```
 $        git remote prune origin
```
If the local copies of deleted branches are not removed by this.

The same effect is achieved by using

```
 $        git fetch --prune
```
