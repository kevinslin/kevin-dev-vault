---
id: QfGCUnAEOlDHGhQvaperc
title: Nohoist
desc: ''
updated: 1635705059708
created: 1635702355385
---

## Summary

Prevent hoisting of dependencies


## Details
- add a `nohoisting` section to workspaces

- NOTE: adding a package to `nohoist` won't remove existing installed packages from `node_modules`
```yml
workspaces: {
  packages: [],
  nohoist: [],
}
```

## Examples

- under a private project root, with nohoist

```json
"workspaces": {
  "packages": ["packages/*"],
  "nohoist": ["**/react-native", "**/react-native/**"]
}
```

- under a private child project, with nohoist: 

```json
"workspaces": {
  "nohoist": ["react-native", "react-native/**"]
}
```

## Syntax

### shallow
```
**/{pkg-name}
```

Example:

- “**/react-native”: this tells yarn not to hoist the react-native package itself, no matter where it is. (shallow)
  - dependencies of react-native will still be hoisted

### deep
```
**/{pkg-name}/**
```

- “**/react-native/**”: this tells yarn not to hoist any of the react-native’s dependent libraries and their dependent libraries. (deep)


## 
- https://classic.yarnpkg.com/blog/2018/02/15/nohoist/
- [Yarn workspaces: nohoist exclude](https://stackoverflow.com/questions/62310476/yarn-workspaces-nohoist-exclude)
- [nohoist with workspaces still hoisting](https://stackoverflow.com/questions/56675874/nohoist-with-workspaces-still-hoisting)
