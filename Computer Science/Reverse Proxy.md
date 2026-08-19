---
tags:
  - concept
  - networking
---
A reverse proxy is **a server that sits in from of [[Web Server]]s and forwards client requests to those web servers**.
This helps in increasing security, performance, and reliability of the information presented by the web servers.
# Isn't That the Same as Forward Proxies?
Contrary to a [[Web Proxy]] or forward proxy, a Reverse Proxy sits in front of the servers, not the clients.
This means **the protection that the proxy provides is given to the servers**, not the clients. This gives different advantages:
- **[[Distributed Denial of Service]] protection**
- **Load Balancing**, where traffic is distributed on multiple servers serving the same page
- **General protection from attacks**, as web servers don't have to expose their real [[IP Address]] that way
- **Caching**
- **SSL/TLS Encryption**, something that is expensive for an origin server
# Forwarding Vs Proxying
I've had some trouble determining the fine line between *routing* a request, and *routing* it. Here is the difference:
Routing is **the decision of knowing where to send the request next**.
Proxying is **the act of actually sending that request there**.
In effect, **routing is the decision, while proxying is the mechanism**.
## Proxying Isn't Forwarding
It's also worth noting that **proxying a request doesn't mean sending it as-is to the next node, or even modifying it before sending it**.
Proxying means **stopping the client's connection at the proxy, and creating a new connection between the proxy and the backend we're going to send the request to**.
The proxy replays the request faithfully, but it's not the same packet. It's reconstructed from scratch on a brand new connection to the server.