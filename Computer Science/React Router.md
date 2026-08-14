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
# Key Concepts
Most of the concepts mentioned here are **documented in the context of the Framework mode**.
## Route Modules
**Files referenced in `routes.ts` are called Route Modules**. These are the foundation of everything React Router.
### Default Export
The default export of a route module **defines the React component that will render when the route matches**.
When that component is rendered, a few things will be passed to it through a `Route.ComponentProps` object:
- `loaderData`: data returned from the loader function in this route module
- `actionData`: data returned from the action function in this route module
- `params`: an object containing the route parameters, if applicable
- `matches`: an array of all the matches in the current route tree
### Loaders
Route loaders **provide data to route components before they are rendered**.
There are client and server loaders, and both can be used together.
In SPA mode, only the client loaders are used.
### Actions
Route actions allow for **server-side data mutation, with an automatic revalidation of all the loader data on the page**. The latter only works with `<Form>`, `useFetcher` and `useSubmit`.
There are also client actions for when you need to call one in the browser.
### Resources
- [React Router Documentation - Route Module](https://reactrouter.com/start/framework/route-module)
## Rendering Strategies
There are three rendering strategies in React Router.
### Client Side Rendering
Routes are **always client-side rendered as the user navigates around the app**.
This is perfect for [[Single Page Application]]s.
### Server Side Rendering
Server side rendering **requires a deployment that supports it**.
While it is technically a global setting, you can enable static pre-rendering for specific routes.
### Static pre-Rendering
Pre-rendering **generates static [[HTML]] and client navigation data for a list of [[Uniform Resource Locator]]s**.
This is useful for [[Search Engine Optimization]] and performance, especially for deployments **without server side rendering**.
### Resources
- [React Router Documentation - Rendering](https://reactrouter.com/start/framework/rendering)
## Actions
Route actions are used for **data mutations**. When they complete, all loader data on the page is revalidated to update the UI with the new data the action just modified.
`action` is called on the server, while `clientAction` runs in the browser.
Client actions **take priority when both server and client actions are defined**.
Actions are called **declaratively from a `<Form>` element**, or imperatively through `useSubmit`.
### Resources
- [React Router Documentation - Actions](https://reactrouter.com/start/framework/actions)
## Outlets
Outlets allow **components to render their child routes' components directly**.
Here is an example to make it clearer: imagine you have a nested route with a dashboard, and two potential child routes, `/dashboard/lobby` and `/dashboard/game/:id`.
Depending on which one you're in, the `<Outlet />` will display that route's component.
So if you're on the lobby view, the outlet will reflect that component, and same with the game view.
The key part is that **the main component (the dashboard) stays the same. Only the child component changes**.
### Resources
- [React Router Documentation - Outlet](https://reactrouter.com/api/components/Outlet)
## Dynamic Segments
**If a path segment of a route begins with `:`**, then it becomes a dynamic segment.
Dynamic segments are **parsed from the URL and given as `params` to router APIs**, allowing your app to display different things based on the dynamic segments.
### Resources
- [React Router Documentation - Dynamic Segments](https://reactrouter.com/start/framework/routing#dynamic-segments)
## Middleware
Middleware **allows you to run code before and after the response generation** for the matched path.
This is particularly useful for logging, authentication, data preprocessing, and error handling.
There are **client and server middleware**, whose sole different is that client middleware don't return response objects, since they're not wrapping an actual [[HyperText Transfer Protocol]] request.
### Resources
- [React Router Documentation - Middleware](https://reactrouter.com/how-to/middleware)
# Resources
- [React Router Documentation](https://reactrouter.com/home)