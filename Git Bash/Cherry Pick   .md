Cherry picking in Git means to choose a commit from one branch and apply it onto another.
This is unlike merge or rebase which generally is used to apply many commits togather onto another branch.

## Step 1:
 - Make sure you are on the branch you want to apply the commit to.

         ``` $ git checkout <branch you want to apply> ```

## Step 2:

         ``` $ git cherry-pick <commit-hash> ```
---
*NOTE: *

If you want to cherry-pick from a public branch, Then must consider using
 
         ``` $ git cherry-pick -x <commit-hash> ```

 - This will generate a standardized commit message by which,
 you and your co-workers can still keep track of the origin of the commit and may avoid merge conflicts in the future.

 - If you have notes attached to the commit they do not follow the cherry-pick. To bring them over as well, You have to use:
         ``` $ git notes copy <from> <to> ```
