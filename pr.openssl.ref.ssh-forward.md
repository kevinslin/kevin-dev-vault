---
id: 4ec9b621-2043-4af0-8504-40e472173249
title: Ssh Forward
desc: ''
updated: 1612475137066
created: 1612475109334
---

## Details
- source [^1]

- WARNING:  You may be tempted to use a wildcard like Host * to just apply this setting to all SSH connections. That's not really a good idea, as you'd be sharing your local SSH keys with every server you SSH into. 
```
Host example.com
  ForwardAgent yes
```

[^1]: https://docs.github.com/en/developers/overview/using-ssh-agent-forwarding