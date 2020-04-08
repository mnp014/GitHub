NOTE: Remember to replace `origin` and `master` with the `remote` and `branch` that you want to synchronize with.

#### Method 1:
```
            $ git fetch origin && git reset --hard origin/master && git clean -f -d
``` 
#### Method 2: (step-by-step)
```
            $ git fetch origin
            $ git reset --hard origin/master
            $ git clean -f -d
```
#### Method 3: (using alias)
##### Step 1: Add as an alias in your `.gitconfig` file:
```
[alias]
    resetorigin = !git fetch origin && git reset --hard origin/master && git clean -f -d
    resetupstream = !git fetch upstream && git reset --hard upstream/master && git clean -f -d
```
##### Step 2: run cmds using alias
```
          $ git resetupstream
```          
or
```
          $ git resetorigin
```
#### Output for all the above 3 methods:
```
          $ git fetch origin && git reset --hard origin/master && git clean -f -d
            HEAD is now at 936dd35 <latest commit message>
            Removing <recently removed files if any/>
          $   
```

