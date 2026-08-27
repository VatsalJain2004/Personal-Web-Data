

# Git & GitHub

## Process / Stages 
#### Working Directory → Staged Area → Local  Repository → Remote Repository 
#### git init or git clone → git add  → git commit -m “” → git push 

git init 
Branching –
   
# Git Branch Commands Cheat Sheet

## Create
### Create a branch
```bash
git branch feature-login
```
Create a branch, but stay on your current branch.

### Create and switch to a new branch
```bash
git switch -c feature-login
```

Create and switch to the new branch.  **Recommended modern syntax.**

**Older equivalent:**
```bash
git checkout -b feature-login
```
----------

## List

### List local branches
```bash
git branch
```

### List local + remote branches
```bash
git branch -a
```

### List only remote branches
```bash
git branch -r
```

### Show branches with their latest commit
```bash
git branch -v
```

### Show branches, latest commits, and upstream/tracking branches
```bash
git branch -vv
```
----------

## Switch

### Switch to a branch
```bash
git switch feature-login
```

**Older:**
```bash
git checkout feature-login
```

### Switch to the previous branch
```bash
git switch -
```
----------

## Rename

### Rename the current branch
```bash
git branch -m new-name
```

### Rename another branch
```bash
git branch -m old-name new-name
```

### If you've already pushed the old name
```bash
git push origin --delete old-name
git push -u origin new-name
```
----------

## Delete

### Delete a merged local branch
```bash
git branch -d feature-login
```

### Force-delete a local branch

```bash
git branch -D feature-login

```

### Delete a remote branch
```bash
git push origin --delete feature-login
```

----------

## Copy/Create from Another Branch

### Create a branch starting from  `develop`
```bash
git branch feature-login develop
```

### Create and switch
```bash
git switch -c feature-login develop
```

----------

## Remote Branch Tracking

### Create a local branch that tracks a remote branch
```bash
git switch -c feature-login --track origin/feature-login
```

### Often Git can infer this
```bash
git switch feature-login
```

### Push a new branch and set its upstream
```bash
git push -u origin feature-login
```

After that, you can usually just use:
```bash
git push
git pull
```
----------

## Useful Inspection Commands

### See which branch you're currently on
```bash
git branch --show-current
```

### See branch relationships
```bash
git log --oneline --graph --all --decorate
```

### See merged branches
```bash
git branch --merged
```

### See branches not merged
```bash
git branch --no-merged
```

----------

## Most Important Ones to Memorize

```bash
git branch                    # list
git branch name               # create
git branch -d name            # delete
git branch -m name            # rename
git switch name               # sw**strong text**itch
git switch -c name            # create + switch
git push -u origin name       # push + track remote
git push origin --delete name # delete remote branch
```

> **Important distinction:**  `git branch`  doesn't switch branches. That's the main thing beginners often mix up.

| Letter | Meaning | What happened |
|---|---|---|
| U | Untracked | New file that Git isn't tracking yet |
| M | Modified | Existing tracked file was changed |
| A | Added | File has been added to the Git staging area |
| D | Deleted | File was deleted |
| R | Renamed | File was renamed |
| C | Conflict | Merge conflict exists |
| ? | Untracked | Similar to `U`, depending on where you're viewing it |
