---
title: Linux
type: docs
math: false
weight: 7
prev: docs/folder/
---

- [Folder sizes](#folder-sizes)
- [Ports in use](#ports-in-use)
- [apps](#apps)




### Folder sizes

```bash
du -h --max-depth=1 .
```

```
1.3G    ./usr
4.0K    ./media
4.0K    ./tmp
4.0K    ./opt
280M    ./app
1.7G    .
```

### Ports in use

```bash
sudo lsof -i -P -n | grep LISTEN
```

```
systemd-r  156 systemd-resolve   14u  IPv4  25682      0t0  TCP 127.0.0.53:53 (LISTEN)
systemd-r  156 systemd-resolve   16u  IPv4  25684      0t0  TCP 127.0.0.54:53 (LISTEN)
node       918             rav   19u  IPv4  19246      0t0  TCP 127.0.0.1:46045 (LISTEN)
docker-pr 6468            root    4u  IPv4  95626      0t0  TCP *:8081 (LISTEN)
docker-pr 6475            root    4u  IPv6  95631      0t0  TCP *:8081 (LISTEN)
docker-pr 6491            root    4u  IPv4  94862      0t0  TCP *:5023 (LISTEN)
docker-pr 6497            root    4u  IPv6  92155      0t0  TCP *:5023 (LISTEN)
docker-pr 6513            root    4u  IPv4  97550      0t0  TCP *:5024 (LISTEN)
docker-pr 6521            root    4u  IPv6  85870      0t0  TCP *:5024 (LISTEN)
```


### apps


```
htop
btop
```


