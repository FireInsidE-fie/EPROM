---
tags:
  - concept
---
Actions in Odoo are **records that define interactions**.
They can be stored in the database, or returned as dictionaries in, for example button methods.
In the global model of Odoo, actions are **the verbs acting on the data**.
Depending on their type (the model they are records of), they might do different things:
- Display a view (`ir.action.act_window`)
- Create a [[PDF]] report (`ir.action.report`)
- Run python code (`ir.action.server`)
- ...
# Resources
- [Odoo 19 Documentation](https://www.odoo.com/documentation/19.0/developer/reference/backend/actions.html)