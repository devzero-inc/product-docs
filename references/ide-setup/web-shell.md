---
title: Web Shell (using GoTTY)
---
# Web Shell (using GoTTY)

There's a [walkthrough video](#walkthrough-video) at the bottom of this page if you want to see how everything looks!

```
version: "3"
build:
  steps:
    - type: apt-get
      packages: ["build-essential", "curl", "git", "nano", "software-properties-common", "ssh", "sudo", "tar", "unzip", "vim", "wget", "zip"]
    - type: command
      command: |
        VERSION=v1.0.1
        wget -O gotty.tar.gz https://github.com/yudai/gotty/releases/download/$VERSION/gotty_linux_amd64.tar.gz
        tar -xvf gotty.tar.gz && rm -rf gotty.tar.gz
        mv gotty /usr/local/bin/gotty

        tee /etc/systemd/system/gotty.service > /dev/null <<EOL
        [Unit]
        Description=GoTTY Service
        After=network.target

        [Service]
        # Starting GoTTY in a mode to allow writing to the shell from the browser, and opening up /bin/bash as default
        ExecStart=/usr/local/bin/gotty -w bash -l
        # Making GoTTY bind to port 7101
        Environment="GOTTY_ADDRESS=0.0.0.0" "GOTTY_PORT=7101" "TERM=xterm-256color"
        Restart=always
        # Making GoTTY session be for the devzero user (instead of `root`)
        User=devzero
        # The shell session will start at this directory
        WorkingDirectory=/home/devzero
        RestartSec=10

        [Install]
        WantedBy=multi-user.target
        EOL

        # Enable the service so it starts on boot
        systemctl enable gotty.service
      user: root
```

## Walkthrough Video

[![Walkthrough Video](https://devzero.b-cdn.net/Web%20shell.mp4)](https://devzero.b-cdn.net/Web%20shell.mp4)
