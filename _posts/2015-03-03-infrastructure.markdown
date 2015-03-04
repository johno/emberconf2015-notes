
layout: post
title:  Bring Sanity to Frontend Infrastructure with Ember 
date:   2015-03-03 16:00:20
categories:
speaker: Sam Selikoff
---

Daya -> API -> Interface

Backends are scalable and consistent.

### Frontend considerations:

* js/css libs
* build pipeline
* data layer
* deployments
* testing

### When the frontend is led astray:

* wastes time
* hard to share
* slow onboarding
* hampers growth

Ember CLI to the rescue, improving infrastructure right away, discover
infrastructure tomorrow.

Creates a consistent, uniform infrastructure. It brings forth conventions.

> Eliminates trivial differences that hold us back

#### Deployment progression

`ember build` -> Script for CI -> Addon -> `ember deploy` -> Deploy server


