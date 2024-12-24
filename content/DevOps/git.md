---
title: GIT
type: docs
math: false
weight: 6
prev: docs/folder/
---

# git helper


## configuracja

```bash
git config pull.rebase true
```

## squash to previous

```bash
git reset --soft HEAD~2 && git commit -m 'squashed'
```


## remote rename

Ustawienie innego brancha jako remote:

```bash
git remote rename origin rpi
git remote rename github origin
git config branch.master.remote origin
```

```bash
cat .git/config
```

```
[branch "master"]
        remote = origin
        merge = refs/heads/master
        vscode-merge-base = origin/master
```


