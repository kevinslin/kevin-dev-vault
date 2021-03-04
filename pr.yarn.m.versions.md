---
id: 9e1d1b70-2919-41b1-8dce-90f8e0d7e127
title: Versions
desc: ''
updated: 1613414758042
created: 1613325468873
---


# 2.x
- source: [^1]
<!-- -->
- Modern features new install strategies, leading projects to only be a fraction of their past self; as an example, under the default configuration the stock CRA artifacts now only take 45MB instead of 237MB. Performances were improved as well, with most installs now only taking a few seconds even on extremely large projects
-  Workspaces are now core components, the resolution pipeline has been streamlined, data structures are more efficient... as a result, Modern is much less likely to suffer from incorrect assumptions and other design flaws

- https://medium.com/@njbmartin/whats-the-problem-with-yarn-2-ca59e3fabc9f
- https://shift.infinite.red/yarn-1-vs-yarn-2-vs-npm-a69ccf0229cd

## Features
- source: [^2]
<!-- -->

- Almost all messages now have their own error codes that can be searched within our documentation 

- workspace aware
    - `yarn up <name>` will upgrade a package in all workspaces at once
    - `yarn add -i <name>` will offer to reuse the same version as the ones used by your other workspaces (and some other choices)
    - The version plugin will give you a way to check that all the relevant workspaces are bumped when one of them is released again.
- zero installs
- `yarn dlx`
    - download and execute
    - always for remote scripts
- `yarn workspaces foreach`
-  New Protocol: patch:
    - this protocol can be used whenever you need to apply changes to a specific package in your dependency tree. 
-  New Protocol: portal: 
    - here the link: protocol is used to tell Yarn to create a symlink to any folder on your local disk, the portal: protocol is used to create a symlink to any package folder.
    - portals follow transitive dependencies, whereas links don't. Even better, portals properly follow peer dependencies, regardless of the location of the symlinked package.
-  Workspace Releases 
    - we've designed a whole new workflow available through a plugin called version. This workflow, documented here, allows you to delegate part of the release responsibility to your contributors. And to make things even better, it also ships with a visual interface that makes managing releases a walk in the park!
-  Workspace Constraints 
    - Constraints offer a way to specify generic rules (using Prolog, a declarative programming language) that must be met in all of your workspaces for the validation to pass.
    -  the following will prevent your workspaces from ever depending on underscore - and will be autofixable!
    ```
    gen_enforced_dependency(WorkspaceCwd, 'underscore', null, DependencyType) :-
  workspace_has_dependency(WorkspaceCwd, 'underscore', _, DependencyType).
    ```
-  Build Dependency Tracking 
    - native packages used to be rebuilt much more than they should have. For example, running yarn remove used to completely rebuild all packages in your dependency tree.
    - we now keep track of the individual dependency trees for each package that lists postinstall scripts, and only run them when those dependency trees changed in some way
-  Per-Package Build Configuration 
    - specify whether a build script should run or not on a per-package basis.
-  Normalized Shell 
    - t knows just enough to give you 90% of the language structures typically used in the scripts field. 
    - `yarn lint \"$@\" && yarn build \"$@\""`
    ```json
    {
    "scripts": {
        "redirect": "node ./something.js > hello.md",
        "no-cross-env": "NODE_ENV=prod webpack"
        }
    }
    ```




```
yarn plugin import workspace-tools
yarn plugin import typescript
```



[^1]: https://yarnpkg.com/getting-started/qa#why-should-you-upgrade-to-yarn-modern
[^2]: https://dev.to/arcanis/introducing-yarn-2-4eh1#cli-output