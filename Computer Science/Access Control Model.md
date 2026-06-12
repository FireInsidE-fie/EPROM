---
tags:
  - security
  - concept
---
A system **controls access to resources** based on a given access control model.
# Discretionary Access Control - DAC
When using DAC, **the resource owner explicitely adds users with the proper permissions**.
Essentially, you add everyone that needs access to a resource manually.
This works fine for a few people, but isn't very scalable.
# Role-Based Access Control - RBAC
This ups the ante on DAC, by introducing *roles*.
**Each role has specific rights**, and instead of assigning rights to users directly, **you assign the roles themselves**.
This has many advantages, including that it's easier to manage permissions: **instead of adding individual permissions for a task, you assign the role for that task**.
# Mandatory Access Control - MAC
This model **prioritizes security above all else**, including ease of use.
Such system are **designed for specific purposes or to handle highly confidential data**.
As such, user friction is minimal, so security can spread its wings more.
## Examples
- [[AppArmor]]
- [[SELinux]]