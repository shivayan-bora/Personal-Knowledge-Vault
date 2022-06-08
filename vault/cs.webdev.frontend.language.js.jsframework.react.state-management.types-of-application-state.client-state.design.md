---
id: u0l1tk4o1kysx28cxpdr2vp
title: Design
desc: ''
updated: 1654588386223
created: 1654540333207
---

Whenever we are designing any kind of UI state management system, we must keep in mind to **keep the state as low as possible**.

The few ways we can design a Client state management system are the following:

1. Local state using `useState` hooks.

2. Lifting the state and then passing down the `props` via `prop` drilling.

3. Global states using `contexts`.

When we are dealing with global states, we can also use Redux, MobX etc.
