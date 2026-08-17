---
tags:
  - concept
abbreviation: RPC
---
An RPC or Remote Procedure Call is **an action where a computer launches a subroutine in a different address space of the current process**. Often, this is on another computer of a network.
The mechanism has to be written similarly as if it was a local call, and the programmer **shouldn't have to care about writing the remote-launching mechanism**.
Still, **distinguishing between remote and local calls is important**, mainly because the former are way slower.
Remote procedure calls are a form of [[InterProcess Communication]].
# Servers and Clients
RPCs are really just a **client-server relationship.** Technically, a client requests the server to execute a bit of code, called a subroutine, with the supplied parameters.
The remote server then **sends a response to the client**, and the latter continues its process normally.
It's basically just another way to call a function, but **instead of calling it in the same process, it happens in another process**.
Of course, one of the main issues with this is the potential network issues that can happen mid-call.
# In Programming Languages
Multiple languages have specific implementations of RPC.
# Protocols
Outside of languages or applications, there exists many protocols to implement RPC.
Here are but a few:
- [[XML-RPC]]
- [[Network File System]]
- [[SOAP]], the successor to XML-RPC
# Resources
- [Wikipedia](https://en.wikipedia.org/wiki/Remote_procedure_call)