---
tags:
  - web/backend
  - framework
---
NestJS is a **backend framework** that wraps [[ExpressJS]] to provide **an architectural wrapper**.
# Key Concepts
## Module
Modules **group related code together, and form the application's overall structure**.
They have imports and exports for other modules, and list two arrays: providers and controllers.
Importing another module makes the current module have access to its providers.
## Controller
Controllers are **what decides which incoming [[HyperText Transfer Protocol]] request runs which function**.
They are the only component with HTTP knowledge.
## Provider
Providers are **where the actual logic of your application lives**.
## Middleware
Middleware functions are **classes (or simple functions) that preprocess requests before it arrives to the controller**.
You define it 
### Restricting Middleware
You can restrict your middleware functions to **only trigger on requests that answer certain conditions**.
Included but not limited to are request routes, request methods, etc.
### Resources
- [NestJS Docs](https://docs.nestjs.com/middleware)
## Exceptions
NestJS has its own exception wrapper layer, which makes sure any exception uncaught by the application code is caught and sent in a clean format to the client.
### Resources
- [NestJS Docs](https://docs.nestjs.com/exception-filters)
## Pipes
Pipes are **classes that have two main use cases**:
1. **Transformation**, as in transforming data to a different form (e.g. from string to integer)
2. **Validation**, as in evaluating whether data is valid or not, and throwing an exception if it's not
Exceptions thrown in Pipe classes aren't handled by the application code, but by the wrapping NestJS layer.
### Resources
- [NestJS Docs](https://docs.nestjs.com/pipes)
## Guards
Guards are classes that are **responsible for checking whether requests will be handled by routes or not**.
This decisions is based on conditions like permissions, roles, ACLs etc. present at run-time.
In effect, they **enforce authorization** (authentication being the identifying the user part).
Guards are executed **after middleware, but before interceptors and pipes**.
### Resources
- [NestJS Docs](https://docs.nestjs.com/guard)
## Interceptors
Interceptors are useful for many different use cases:
- Executing logic after or before method execution
- Transforming a function's results
- Transforming a function's exception
- Extending the function's base logic
- Overriding a function completely based on specific conditions (like for caching)
### Resources
- [NestJS Docs](https://docs.nestjs.com/interceptors)