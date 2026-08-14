---
tags:
  - language
---

# Modules
## CommonJS Vs ESM
Back in the day, modules didn't exist as we know them today.
It was a wild west of globals and function calls.
So, [[Node.js]] stepped in and created *CommonJS*.
### Common JS
CommonJS uses **function calls to import stuff**, `require()`.
It resolves the target module synchronously, and returns a value with everything of the module inside.
That means the **module graph is discovered at runtime**.
### ES Modules
ES Modules were the solution the language itself standardized.
It uses `import` and `export` statements, with default exports an imports, named imports, etc.
Contrary to CJS, `import` isn't a statement: **it's a declaration**. That means it's verified and resolved before any code executes.
This has the neat side-effect of **allowing tree-shaking, where unused stuff in a module just isn't imported at all**.
## Resources
- [javascript.info's page on modules](https://javascript.info/modules-intro)