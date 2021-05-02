---
id: ae2b4df5-70a8-4ff1-9811-50766e422961
title: Cook
desc: ''
updated: 1619890393118
created: 1619890330328
---


### selective version resolution
- source: [^res]
<!-- -->
[^res]: https://classic.yarnpkg.com/en/docs/selective-version-resolutions/

- define custom package versions or ranges inside your dependencies


```json
{
  "name": "project",
  "version": "1.0.0",
  "dependencies": {
    "left-pad": "1.0.0",
    "c": "file:../c-1",
    "d2": "file:../d2-1"
  },
  "resolutions": {
    "d2/left-pad": "1.1.1",
    "c/**/left-pad": "^1.1.2"
  }
}
```