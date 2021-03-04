---
id: 012bda0e-ecfb-4b2e-a7cd-2b75b77e3003
title: Window
desc: ''
updated: 1612724649727
created: 1612650742872
---

### setInterval
- source: [^1]
<!-- -->

- set and clear interval
```js
var myVar = setInterval(myTimer, 1000);

function myTimer() {
  var d = new Date();
  var t = d.toLocaleTimeString();
  document.getElementById("demo").innerHTML = t;
}

function myStopFunction() {
  clearInterval(myVar);
} 

```

### setTimeout

- `(f: ()=>void | FuncString, [timeInMs: int])`
- scoping
    - https://stackoverflow.com/questions/5779576/in-javascript-what-is-the-scope-of-variables-used-in-settimeout

- schedule function for later time

```
setTimeout(function() { doSomething(var1); }, 10000);


```

- scoping
    - https://stackoverflow.com/questions/5779576/in-javascript-what-is-the-scope-of-variables-used-in-settimeout
[^1]: https://www.w3schools.com/jsref/met_win_setinterval.asp
