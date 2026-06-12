---
tags:
  - web/backend
  - framework
---
NestJS is a **backend framework** that wraps [[ExpressJS]] to provide **an architectural wrapper**.
# Key Concepts
## IoC Container
The Inversion of Control Container is **responsible for start-up creation and plumbing of a NestJS backend**.
It wires the backend as the modules define it (imports and exports), wiring providers and controllers together and then handing the structure off to the runtime Router and HTTP Server.
## Module
Modules **group related code together, and form the application's overall structure**.
They have imports and exports for other modules, and list two arrays: providers and controllers.
Importing another module makes the current module have access to its providers.
Modules **don't exist at runtime, and are only there for organization purposes**.
## Controller
Controllers are **what decides which incoming [[HyperText Transfer Protocol]] request runs which function**.
They are the only component with HTTP knowledge, and the Nest router uses this to route requests to the right controller, according to the paths they define in their methods' decorators.
## Provider
Providers are **where the actual logic of your application lives**.
They are called by controllers.
## Middleware
Middleware functions are **classes (or simple functions) that preprocess requests before it arrives to the controller**.
They are especially good for things that should happen to requests **before they get processed at all**, like logging.
### Restricting Middleware
You can restrict your middleware functions to **only trigger on requests that answer certain conditions**.
Included but not limited to are request routes, request methods, etc.
### Resources
- [NestJS Docs](https://docs.nestjs.com/middleware)
## Exception Filters
NestJS has its own exception wrapper layer, which **makes sure any exception uncaught by the application code is caught and sent in a clean format to the client**.
It sits under the general flow of `middleware -> guard -> interceptor (in) -> pipe -> handler -> interceptor (out) -> response` to **catch any exception that escapes the flow and creates an error response out of it**.
This happens, for example, **when a guard or a pipe fails a request**. The exception filter catches that exception, and creates an HTTP response that the Nest HTTP server can send back to the client.
### Resources
- [NestJS Docs](https://docs.nestjs.com/exception-filters)
## Pipes
Pipes are **classes that have two main use cases**:
1. **Transformation**, as in transforming data to a different form (e.g. from string to integer)
2. **Validation**, as in evaluating whether data is valid or not, and throwing an exception if it's not
Exceptions thrown in Pipe classes aren't handled by the application code, but by the wrapping NestJS layer.
Pipes are **especially useful to confirm that requests are well-formed**.
### Resources
- [NestJS Docs](https://docs.nestjs.com/pipes)
## Guards
Guards are classes that are **responsible for checking whether requests will be handled by routes or not**.
This decision is based on conditions like permissions, roles, ACLs etc. present at run-time.
In effect, they **enforce authentication and authorization**.
Guards are executed **after middleware, but before interceptors and pipes**.
### Resources
- [NestJS Docs](https://docs.nestjs.com/guard)
## Interceptors
Interceptors are ways to run code to **wrap the handler of the request**, running either after the guard on the way in, or after the handler on the way out.
Interceptors are useful for many different use cases:
- Executing logic after or before method execution
- Transforming a function's results
- Transforming a function's exception
- Extending the function's base logic
- Overriding a function completely based on specific conditions (like for caching)
### Resources
- [NestJS Docs](https://docs.nestjs.com/interceptors)