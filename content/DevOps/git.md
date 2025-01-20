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

## squash current with to previous

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



# Hugging Face

https://huggingface.co/docs/transformers/en/quicktour


```bash
conda create -n tr python=3.12
conda activate base
conda activate tr
conda deactivate
conda remove -n tr --all
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
pip list
https://huggingface.co/docs/transformers/en/quicktour
conda install spyder
pip install jupyter
pip install ipywidgets widgetsnbextension pandas-profiling
pip install transformers datasets evaluate accelerate
```
