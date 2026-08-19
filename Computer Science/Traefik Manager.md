---
tags:
  - tool/network
---
Traefik Manager is a **self-hosted UI for managing and monitoring your [[Traefik]] reverse proxy**.
It allows you to avoid editing the Traefik dynamic config's YAML directly, instead going it through a web UI.
# File Provider
The dynamic distinction is important. **Traefik Manager is not a provider for Traefik**.
Instead, it **writes the `dynamic.yml` file of the file provider, essentially editing another provider** through a web UI instead of modifying the file directly.
It **cannot edit other provider's configuration**.
However, it can edit the static configuration found in `traefik.yml` if you add its bind mount to the container (or just give TM access to the file somehow).
# Resources
- [Traefik Manager Official Docs](https://traefik-manager.xyzlab.dev/guide.html)