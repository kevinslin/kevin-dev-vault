---
id: aef3d2e7-9291-4950-b24b-4660d60a86b3
title: Concepts
desc: ''
updated: 1609996895808
created: 1609996768710
---


### Events 

-represent actions users have taken [^1]

```
amplitude.getInstance().logEvent(‘play song’);
```


### Event Properties

- Event Properties give you context about events, like where in your app they occur or what state the app is in when it occurred.

```js
amplitude.getInstance().logEvent('play song',
    { title: 'Here comes the Sun',
      artist: 'The Beatles', genre: 'Rock'});
```

### User Sessions

- User Sessions allow you to track series of events that are performed within a single visit or interaction with your application.
- Most often, Amplitude keeps track of session automatically for you. 

### User Properties 
- User Properties help understand your User at the time they performed actions within your application. What state they were in, their preferences, or their device details, are all examples of common user properties.-

```js
var identify = new amplitude.Identify().set('plan', 'premium');
amplitude.getInstance().identify(identify);
```


---

[^1]: [How Amplitude Works](https://developers.amplitude.com/docs )