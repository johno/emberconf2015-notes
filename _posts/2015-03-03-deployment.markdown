---
layout: post
title:  The Art of Ember Deployment 
date:   2015-03-03 14:15:20
categories:
speaker: Luke Melia
---

Software delivery has evolved. We now have the browser -- the most ubiquitious app runtime
in the world.

> The future is already here -- it's just not very evenly distributed - William Gibson

Server web app deployment:

* Deploy latest files
* Refresh

Is the "server app" deployment right for Ember apps? __No.__

Keep static assets working during rolling restarts:

Both old and new must be available. Cache old assets on the CDN for a while. However, the SPA
may remain on a single session (page load) for 5, 10, 15 minutes. This can result in a 500.

# API needs to remain backwards compatible for at least the length of a user session.

Versioning Ember apps and Server APIs together is a lie. This should work more similarly to
a native mobile app.

Results in freedom, reduces coupling.

The HTML dictates the version of the app to launch:

* Point to fingerprinted JS/CSS.
* Contains JS URLS to boot JS app and load CSS in the correct order.
* Provide environment specific information.
* Minimal to no caching.

HTML should be managed and deployed as part of the static asset deployment process. Shouldn't be
deployed by the API server (API shouldn't be re-deployed for asset changes).



