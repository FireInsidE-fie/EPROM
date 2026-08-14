---
tags:
  - library
---
Passport is **a simple authentication library and middleware for [[Node.js]]**.
Its primary purpose to is to **authenticate requests**.
# Important Concepts
## Middleware
Passport is **used as so called *middleware* in a web application to authenticate requests**.
Middleware was popularized in [[Node.js]] by [[ExpressJS]].
It's particularly useful for APIs that need to obey [[REpresentational State Transfer]] (REST) constraints.
Essentially, **middlewares are a chain, with each `next()` call in Express leading to the next middleware** function in the chain.
That also means that, since middleware are nested, they can run code before and after other middleware run. Kinda like a recursion trail!
```js
app.post('/login/password',
	passport.authenticate('local', { failureRedirect: '/login', failureMessage: true }),
	function(req, res) { res.redirect('/~' + req.user.username); });
```
In this example, `passport.authenticate` will run before the other function, and if it fails, the latter won't be run at all; we'll redirect to `/login` instead.
On success, it **attaches the authenticated user to `req.user` so later stages can use it**.
## Strategies
Strategies are **responsible for authenticating requests**. They accomplish this by implementing an *authentication mechanism*.
Authentication mechanisms **define how to encode a credential in a request**. This could be a passport, or an assertion by a different provider, in the case of [[OAuth 2.0]].
They also **define the procedure to verify that credential**.
### Installation
You install strategies **using the appropriate [[npm]] package**.
### Configuration
#### First Steps
Once a strategy is installed, **it needs to be configured**.
The configuration varies with each authentication mechanism, so each strategy should have its own documentation detailing the available configuration options.
#### Verify Function
In many strategies, **a verify function is taken in the strategy constructor**.
This function's job is to **parse the credential contained in the request**, and well… verify it.
Concretely, it **determines the user to which that credential belongs**.
This allows the strategy to effectively delegate the actual data access to the app. Instead of checking the user records itself, the app does with its verify function.
The verify function is **strategy-specific, with each strategy giving different arguments**.
Its job might be different for each strategy too!
For strategies involving shared secrets instead of a password, a verify function might be responsible for verifying the credential and then yielding a user. For cryptographic authentication, it might yield a user and a key.
Always rely on the strategy's documentation!
As to what it returns, the verify function **always calls the callback function**. It has three states: failure, success, or server error.
On success, it'll give the user to the callback function. On failure, false is given instead. On errors, the error is given.
#### Registration
Once a strategy has been configured, it can be registered by calling `passport.use()`.
You can even rename it by passing a name before the strategy.
```js
let passport = require('passport');
passport.use('password', strategy);
```
### Usage
Once configured and registered, the strategy can be employed to authenticate a request by **passing the name of the strategy to the `passport.authenticate()` middleware**.
## Sessions
Since [[HyperText Transfer Protocol]] is stateless, we need a way to identify users across multiple pages, over time. Enter sessions.
They **allow state to be maintained between the application server and the user's browser**.
A session is **established by setting a Cookie ([[HyperText Transfer Protocol#Cookies]]) in the browser**.
The server then uses the cookie the browser sends to retrieve information it needs across multiple requests, like user ids.
This **adds state on top of HTTP**.
# Resources
- [Passport's Documentation's Overview](https://www.passportjs.org/concepts/authentication/downloads/html/)