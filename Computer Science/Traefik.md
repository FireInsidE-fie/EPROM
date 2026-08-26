---
tags:
  - tool/network
---
Traefik is a [[Reverse Proxy]] and [[Load Balancer]]. It can serve many purposes, including service discovery.
It is the core of the *Traefik Hub Runtime Platform*, the ecosystem of other Traefik products.T
# Core Concepts
Traefik has a few main concepts that help understand how it works.
## Entrypoints
Entrypoints are **the network entry points into Traefik.** They define the ports that receive the requests, and whether it's on [[Transmission Control Protocol]] or [[User Datagram Protocol]].
## Routers
Routers are **tasked with proxying requests to the services that handle them.**
While doing so, routers may use **pieces of middleware to update the request or do stuff before it arrives to the final service**.
Routers' job is to check a request's host header, and from the configured routes, ask the right service.
**Traefik doesn't rewrite the requests**. Instead, they stop at the proxy, and the services are queried using the protocol defined in your route.
## Services
Services **define how to actually reach the services that will handle the requests**.
These describe the port, protocol, and location of the service. You could have a request arrive at the proxy through HTTPS, and the service be queried through raw HTTP.
The protocol is called the *backend scheme*.
These are load-balanced, with optional health checks.
## Providers
Providers are **infrastructure components**, like orchestrators, container engines, cloud providers, key-value stores…
**Traefik will query the provider APIs to find information about routing**.
This is how routing information arrives to Traefik.
When it detects a change, **it will dynamically update its routes**.
### Docker Labels and ECS
For example, for Docker, it will just connect to Docker and listen to labels found on the container configurations that begin with `traefik.`.
For example, in the other container you want Traefik to look at:
```yaml
services:
	my-service:
		image: my-image
		labels:
			- "traefik.http.routers.my-router.rule=Host(`example.com`)"
			- "traefik.http.services.my-service.loadbalancer.server.port=80"
```
### File Provider
Or, you could just use the file provider, and provide a [[YAML]] or [[TOML]] file with routing information. This is **very useful for services without a way to expose information to Traefik**.
You enable it by **setting its directory in the configuration**. The file is named `dynamic.yml`.
```yaml
providers:
	file:
		directory: "/path/to/dynamic/conf"
```
### Resources
- [Official Traefik Documentation](https://doc.traefik.io/traefik/reference/routing-configuration/dynamic-configuration-methods/)
  Here are listed the other dynamic configuration methods.
## TLS Certificates
Treafik, by its job and nature, **terminates [[Transport Layer Security]] connections**. It's the endpoint of the encrypted connection, so the latter ends here.
As such, **it needs a private key and certificate for every hostname it serves over [[HTTPS]]** when sending data back.
For this, Treafik can manage [[Certificates]].
### ACME
Traefik uses an `acme.json` file to manage **certificates issued and renewed automatically by Traefik's [[ACME]] resolver.** That could be [[Let's Encrypt]], [[ZeroSSL]], or others.
### File-Based
You can also **provide your own certificates through files**.
# Deployment
Traefik can be **deployed using [[Docker]] or [[Kubernetes]]**.
If you use [[Traefik Manager]], install the `tm` utility to manage the whole stack.
# Configuration
Configuration in Traefik is two-fold:
- The *install configuration* (otherwise known as the *static configuration*): Set up connections to providers, and define the entrypoints. These don't change often.
  `traefik.yml`
- The *routing configuration* (otherwise known as the *dynamic configuration*): Defines how the requests are handled by your system. This one often changes, and is hot-reloaded without any interruption to the service.
  `dynamic.yml`, through the file provider
## Routing Configuration
Traefik gets its routing configuration **from providers**. That could be an orchestrator, or a service registry, or just a configuration file it finds somewhere.
## Install Configuration
There are **three ways to define the install configuration of Traefik**. However, only one can be used at a time.
1. In a configuration file
2. In the command-line arguments
3. As environment variables
The evaluation happens in that order.
### Configuration File Location
- `/etc/traefik`
- `$XDG_CONFIG_HOME`
- `$HOME/.config/`
- `.` (the current working directory)
You can override this with the `--configFile` argument.
# See Also
- [[Traefik Manager]]
# Resources
- [Traefik Documentation](https://doc.traefik.io/traefik/)