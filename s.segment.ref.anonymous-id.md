---
id: 5c464ad2-7521-41b1-9861-6d11943102f7
title: Anonymous Id
desc: ''
updated: 1610839758789
created: 1610839607379
---


## Resources
- https://segment.com/docs/connections/sources/catalog/libraries/website/javascript/identity/


## Generation
- Tip! Only the Segment mobile and website libraries automatically generate an anonymousId. If you use Segment’s Server libraries, you must generate an anonymousId manually. It can be any pseudo-unique identifier, for example you might use a sessionId from a backend server. [^1]


## When it changes
- The user clears their cookies and localstorage.
- Your site or app calls `analytics.reset()` during in the user’s browser session.
- Your site or app calls `analytics.identify()` with a userId that is different from the current userId.

[^1]: https://segment.com/docs/connections/spec/best-practices-identify/