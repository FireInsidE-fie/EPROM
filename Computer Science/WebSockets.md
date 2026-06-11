---
tags:
  - web
---
WebSockets was borne out of a necessity for easy two way communication where **the server can just send stuff umprompted to the client**.
This happens through a persistent connection, during which the server can broadcast any information it deems fit to the client, **without the client issuing a request first**.
# How It Works
The base idea of a WebSocket connection is that it **starts over [[HyperText Transfer Protocol]], and then transfers over to the WebSockets protocol**.