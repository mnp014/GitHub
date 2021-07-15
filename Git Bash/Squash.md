# Method 1
## Step 1:
```
            $ git rebase -i master
```
## Step 2:
- now replace **pick** with **s** and save it using **wq!** 

## Step 3:
- Continue the rebase and resolve conflicts if any
```
            $ git rebase --continue
```

## Step 4:
- Remove unnecessary comments.

## Step 5:
- Complete the rebase.
```
            When success message : Successfully rebased and updated refs/heads/<Curr_branch_name>
            
            $ git push -f origin <Curr_branch_name>
```
___
---
# Method 2
## Step 1:
- Do an interactive rebase involving the **N** commits.<br />
``` 
            git rebase -i HEAD~<N>
```
Example:<br />

```
            git rebase -i HEAD~4
```

This tells Git that you want to do an interactive rebase involving the **FOUR commits**.<br />
including and counting backwards from the HEAD of your branch.<br /><br />

This should show you a list looking something like the following:

```
            pick 0d229f4 Commit 1
            pick 2be75bc Commit 2 (part 1)
            pick fa52bc9 Commit 2 (part 2)
            pick f23eabc Commit 3
```

*Note the oldest commit appears first, and the most recent of the four commits appears last.*
## Step 2:
- Change the **pick** for the *middle commit part 2* you want to combine with *part 1* to **squash**:

```
            pick 0d229f4 Commit 1
            pick 2be75bc Commit 2 (part 1)
          squash fa52bc9 Commit 2 (part 2)                // Replace "PICK" with "SQUASH"
            pick f23eabc Commit 3
```
Squashing means combining a commit labelled with **squash** into the *commit* above it, in this case **merging part 2 into part 1**.
## Step 3:
- **Save** the file and **Exit** the editor
## Step 4:
- Continue the rebase and resolve conflicts if any
```
            $ git rebase --continue
```
## Step 5:
- Complete the rebase.
```
            When success message : Successfully rebased and updated refs/heads/<Curr_branch_name>
            
            $ git push -f origin <Curr_branch_name>
```
## Outcome:

```
            pick 0d229f4 Commit 1
            pick 2be75bc Commit 2 (part 1)
            pick f23eabc Commit 3
```


**Note:** *Rewriting the history of a public branch can cause problems for anyone besides you who is using this branch. So you might want to avoid using this method if this situation applies to you.*
