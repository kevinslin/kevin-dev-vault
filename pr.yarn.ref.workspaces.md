---
id: 2a1723c7-d943-4134-98fb-bb403f123d27
title: Workspaces
desc: ''
updated: 1621823844912
created: 1613284726208
---

## Summary
- source: [^1]
<!-- -->
- allows you to setup multiple packages in such a way that you only need to run yarn install once to install all of them in a single pass
- features
    - Your dependencies can be linked together,
    - All your project dependencies will be installed together
    - Yarn will use a single lockfile 

## Details
- after putting

## Quickstart

- package.json

```json
{
  "private": true,
  "workspaces": ["workspace-a", "workspace-b"]
}
```

## Tips
- If you’re only making changes to a single workspace, use –focus to quickly install sibling dependencies from the registry rather than building all of them from scratch.

## Gotchas
- In the example above, if workspace-b depends on a different version than the one referenced in workspace-a’s package.json, the dependency will be installed from npm rather than linked from your local filesystem


## Focused Workspaces
- source: https://classic.yarnpkg.com/blog/2018/05/18/focused-workspaces/

## FAQ

### comparison to lerna
Yarn’s workspaces are the low-level primitives that tools like Lerna can (and do!) use. They will never try to support the high-level feature that Lerna offers


### no hoisting
- add a `nohoisting` section to workspaces

- NOTE: adding a package to `nohoist` won't remove existing installed packages from `node_modules`
```yml
workspaces: {
  packages: [],
  nohoist: [],
}

```

## Cook

### Focused workspace
- url: https://yarnpkg.com/blog/2018/05/18/focused-workspaces/

- available for 1.7.0
- install sibling dependencies shallowly
- faster when you are working with single packages

[^1]: https://classic.yarnpkg.com/en/docs/workspaces/

### ignore workspaces
- https://github.com/yarnpkg/yarn/issues/4099
- [Yarn workspaces: nohoist exclude](https://stackoverflow.com/questions/62310476/yarn-workspaces-nohoist-exclude)
- [yarn-isolate-workspace](https://www.npmjs.com/package/yarn-isolate-workspace)
