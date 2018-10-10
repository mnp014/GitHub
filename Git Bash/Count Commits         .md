# Count the number of commits on a Git branch
---
- To count the commits for the branch you are on:
```
        $ git rev-list --count HEAD
```
---
- For a particular branch
```
        $ git rev-list --count <branch-name>
```
---
- Count the commits on a branch that are made since the creation of the branch
```
        $ git rev-list --count HEAD ^<branch-name>
```
- [This will count all commits ever made that are not on the branch-name as well.]
---

# Examples 1:
- master with 3 commits

```
        $ git checkout master
        $ git checkout -b test
        $ git rev-list --count HEAD ^master
```
```
        Result: 3
```
---
# Examples 2:
- If a branch comes of a branch called MyBranch with 3 commits.

```
        $ git checkout MyBranch
        $ git checkout -b test
        $ git rev-list --count HEAD ^MyBranch
```
```
        Result: 3
```

- Ignoring Merges
  - If you merge another branch into the current branch without fast forward and
   you do the above, the merge is also counted. This is because for git a merge is a commit.
   
  - If you don't want to count these commits add --no-merges:

```
        $ git rev-list --no-merges --count HEAD ^MyBranch
```
