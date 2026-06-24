---
tags:
  - web/frontend
  - library
---
React Router is a **library for [[React]] that allows you to implement client-side routing for [[Single Page Application]]s written in React**.
Since React itself has no concept of routing or URLs, you either need a framework like [[Next.js]], or a library like React Router to do that job.
# How It Works
React Router sits on **two API primitives modern browsers expose**:
- `history.pushState(null, '', '/path'`
  This allows your application to update the URL a browser shows, without the browser actually querying that URL.
  This is perfect to enable back/forward buttons for your application.
- `window.addEventListener('popstate', () => { /* your code */ });`
  This listens to the `popstate` event, something the browser sends when the URL it has changes (the back/forward buttons are pressed).
  This allows you to react (no pun intended) to state changes, and change what's displayed accordingly.
React Router abstracts away those things, by 
# Resources
- [React Router Documentation](https://reactrouter.com/home)