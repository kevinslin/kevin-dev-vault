---
id: de57be03-8806-4cc1-b799-8e57b38c233e
title: Lifecycle
desc: ''
updated: 1633638710538
created: 1621292264400
---

## Summary
- source: [^1]
<!-- -->



- new user: is one who has logged the event you specified in Step One above for the first time. 
- current user is one who was active in the previous usage interval (day, week, or month)
- resurrected user is an active user who was not active for the previous interval (day, week, or month), or longe
- dormant user is one who did not log the event you've specified, but who was active during the previous time period

## Details
- NOTE: You can only include one event in a lifecycle analysis.
- NOTE: You can only include one user segment in a lifecycle analysis.
- narrow your focus even further by telling Amplitude you only want to include users who have already performed certain actions

## Types

### Growth
-  distribution of active users and the count of dormant users for a particular day, week, or month

### Dormant
- distribution of dormant users for a particular day, week, or month
- eg. dormant new user on August 10th (shown in the bar between August 9th and August 10th) is a user who was new on August 9th but became dormant on August 10th

### Pulse
- ratio of incoming (new and resurrected) users to outgoing (dormant) users for a particular day, week, or month
- `(# of new users + # of resurrected users) / (# of dormant users)`


## Citations
[^1]: https://help.amplitude.com/hc/en-us/articles/228838627-The-Lifecycle-chart-track-the-growth-of-your-product-s-user-base