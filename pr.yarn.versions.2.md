---
id: 16a4f7b2-eb83-44de-a109-fc77fd2d3365
title: '2'
desc: ''
updated: 1613413640331
created: 1613413539856
---

## Summary
- source: [^1]
<!-- -->

* Run npm install -g yarn to update the global yarn version to latest v1
* Go into your project directory
* Run `yarn set version berry` to enable v2 (cf Install for more details)
* If you used .npmrc or .yarnrc, you'll need to turn them into the new format (see also 1, 2)
* Add nodeLinker: node-modules in your .yarnrc.yml file
* Commit the changes so far (yarn-X.Y.Z.js, .yarnrc.yml, ...)
* Run yarn install to migrate the lockfile
* Take a look at this article to see what should be gitignored
* Commit everything remaining

```
npm install -g yarn@latest
yarn set version berry

```

[^1]: https://next.yarnpkg.com/getting-started/migration#step-by-step
