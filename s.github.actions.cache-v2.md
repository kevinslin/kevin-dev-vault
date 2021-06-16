---
id: X2GZB78MoEOyChWkldL9d
title: Cache V2
desc: ''
updated: 1623688106737
created: 1623688013739
---


## Summary
- https://github.com/actions/cache


## Cook

### generate cache key
```yml
- uses: actions/cache@v2
with:
	path: | 
	path/to/dependencies
	some/other/dependencies 
	key: ${{ runner.os }}-${{ hashFiles('**/lockfiles') }}
```