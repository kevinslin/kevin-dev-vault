---
id: b9db8201-8262-4c1a-8ef5-eeb2b2516241
title: Nunjucks
desc: ''
updated: 1613967854714
created: 1613929367199
---

## Summary
- source: [^1]
<!-- -->

- basics
```njs
{% extends "base.html" %}

{% block header %}
<h1>{{ title }}</h1>
{% endblock %}

{% block content %}
<ul>
  {% for name, item in items %}
  <li>{{ name }}: {{ item }}</li>
  {% endfor %}
</ul>
{% endblock %}
```

- filters
```njs
{{ foo | title }}
{{ foo | join(",") }}
{{ foo | replace("foo", "bar") | capitalize }}
```

- keywords
```njs
{{ foo(1, 2, bar=3, baz=4) }}
{{ bar | transform(level=2) }}
```

- create
```njs
var res = nunjucks.render('foo.html');

var res = nunjucks.render('foo.html', { username: 'James' });

nunjucks.render('async.html', function(err, res) {
});
```

[^1]: https://mozilla.github.io/nunjucks/