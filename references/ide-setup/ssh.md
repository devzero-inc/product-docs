---
title: SSH
---
# SSH

First, get the name of the workspace that you want to connect VS Code to...

```
# to get the workspace name
dz workspace ls
```

Then, run ...

```
dz workspace connect <workspace-name>

# if your workspace is called absconding-rhino-mega
dz workspace connect absconding-rhino-mega
```

Or if you prefer you can connect via SSH client

```
# if your workspace is called absconding-rhino-mega
ssh devzero@absconding-rhino-mega
```
