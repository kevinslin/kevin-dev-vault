---
id: 432d4939-71c6-44e7-919f-1e7c8822d5c7
title: Cook
desc: ''
updated: 1620690996427
created: 1612474883509
---


### Use Proxy Command

```sh
ssh -i path/to/ssh -o ProxyCommand="ssh -i path/to/ssh ec2-user@{SOME_IP} 'nc %h %p'" ec2-user@{PRIVATE_IP} -vvv
```

### Restart
- source: [^restart]
<!-- -->

[^restart]: https://askubuntu.com/questions/462968/take-changes-in-file-sshd-config-file-without-server-reboot

```
sudo /etc/init.d/sshd restart
```
