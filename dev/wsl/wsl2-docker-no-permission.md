---
tags:
  - dev
  - docker
  - wsl2
  - fix
created_at: 2023-09-28 07:10
aliases:
  - "2023-09-28"
---
## Problem
when trying to run `docker pull oven/bun:alpine`, it had an error
```
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: ...
```

## Solution
- add docker to user groups `sudo usermod -aG docker $USER`
- based on [this website](https://dev.to/kenji_goh/got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket-3dne)
- no need to install docker since it is already from WSL2

useful in fixing problems regarding docker permissions