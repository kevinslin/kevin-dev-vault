---
id: ea88d5f4-f73f-4332-be56-441432a30d0e
title: Segment
desc: ''
updated: 1610839602420
created: 1610472081457
---

# FAQ

### What is the difference between Segment and tag managers? 
- [source](https://segment.com/docs/guides/segment-vs-tag-managers/)

- Tag managers primarily focus on ad networks, and can’t support modern tools without extensive customization.



# Node
- https://segment.com/docs/connections/sources/catalog/libraries/server/node/

### identify 
-  call identify once when the user’s account is first created, and then again any time their traits change.

```js
analytics.identify({
  anonymousId: '48d213bb-95c3-4f8d-af97-86b2b404dcfe',
  traits: {
    friends: 42
  }
});
```

- identified user
```js
analytics.identify({
  userId: '019mr8mf4r',
  traits: {
    name: 'Michael Bolton',
    email: 'mbolton@example.com',
    plan: 'Enterprise',
    friends: 42
  }
});
```

### track
- record the actions your users perform. Every action triggers what we call an “event”, which can also have associated properties.


```js
analytics.track({
  anonymousId: '48d213bb-95c3-4f8d-af97-86b2b404dcfe',
  event: 'Item Purchased',
  properties: {
    revenue: 39.95,
    shippingMethod: '2-day'
  }
});
```

### page
- record page views on your website, along with optional extra information about the page being viewed

```js
analytics.page({
  userId: '019mr8mf4r',
  category: 'Docs',
  name: 'Node.js Library',
  properties: {
    url: 'https://segment.com/docs/connections/sources/catalog/librariesnode',
    path: '/docs/connections/sources/catalog/librariesnode/',
    title: 'Node.js Library - Segment',
    referrer: 'https://github.com/segmentio/analytics-node'
  }
})
```

### group 
lets you associate an identified user with a group. A group could be a company, organization, account, project or team! It also lets you record custom traits about the group, like industry or number of employees.


```js
analytics.group({
  userId: '019mr8mf4r',
  groupId: '56',
  traits: {
    name: 'Initech',
    description: 'Accounting Software'
  }
});
```

### alias
- The alias call allows you to associate one identity with another. This is an advanced method and should not be widely used, but is required to manage user identities in some destinations. Other destinations do not support the alias call.

### configuration

```js
var analytics = new Analytics('YOUR_WRITE_KEY', {
  flushAt: 20,
  flushInterval: 10000
});
```

- for dev
```js
var analytics = new Analytics('YOUR_WRITE_KEY', { flushAt: 1 });
```

### select destinations

```js
analytics.track({
  event: 'Membership Upgraded',
  userId: '97234974',
  integrations: {
    'All': false,
    'Vero': true,
    'Google Analytics': false
  }
})
```