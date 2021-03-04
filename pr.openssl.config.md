---
id: cfd24707-8412-4743-a6d2-b4f29f890ca3
title: Config
desc: ''
updated: 1612475924363
created: 1612474938890
---


## Layout
- /etc/ssh/ssh_config: client config
- /etc/ssh/sshd_config: server config

## Client

### ClientAliveInterval
- num sec server will wait before sending null packet to client

### ServerAliveInterval
- num seconds client will wait before sending null packet to server
    - setting value to 0 (default) will disable feature

### ProxyCommand
- http://www.cyberciti.biz/faq/linux-unix-ssh-proxycommand-passing-through-one-host-gateway-server/

- connect to one host via intermediary

## Server

- common
```
X11Forwarding yes
AllowAgentForwarding yes
PermitRootLogin yes
```

##  ENV
- SSH_AUTH_SOCK: location of ssl socket

## Variables
- https://unix.stackexchange.com/questions/183951/what-do-the-h-and-p-do-in-this-command
<!-- -->
- %h: hostname
- %p: port
- %r: remote user name
