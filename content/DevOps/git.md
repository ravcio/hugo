# git helper

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


