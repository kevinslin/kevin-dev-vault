---
id: 5ol8plBZcZDJwci9RY1BX
title: Deno
desc: ''
updated: 1643315569229
created: 1643314944064
---


# Linking to third party code 
- https://deno.land/manual@v1.18.1/linking_to_external_code

## Caching
- deno caches in `DENO_DIR`
* On Linux/Redox: $XDG_CACHE_HOME/deno or $HOME/.cache/deno
* On Windows: %LOCALAPPDATA%/deno (%LOCALAPPDATA% = FOLDERID_LocalAppData)
* On macOS: $HOME/Library/Caches/deno
- if something fails, it falls back to $HOME/.deno

## deps.ts

- deps.ts
```ts
export {
  assert,
  assertEquals,
  assertStringIncludes,
} from "https://deno.land/std@0.123.0/testing/asserts.ts";
```

```ts
import { assertEquals, runTests, test } from "./deps.ts";
```

# NPM
- https://deno.land/manual@v1.18.1/npm_nodejs

### differences
- Deno doesn't require an external meta-data file to function or resolve modules.

### limitations
-  Deno only supports ES Modules