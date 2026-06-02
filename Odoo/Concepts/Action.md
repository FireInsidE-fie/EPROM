---
tags:
  - concept
  - odoo
---
Actions in Odoo are records that **define interactions**.
In the global model of Odoo, actions are **the verbs** acting on the data.
Depending on their type (the model they are records of), they do different things:
- Display a view (`ir.action.act_window`)
- Create a [[PDF]] report (`ir.action.report`)
- Run python code (`ir.action.server`)
- 