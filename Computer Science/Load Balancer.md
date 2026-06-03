---
tags:
  - concept
  - networking
---
A load balancer is **hardware or software that performs load balancing**.
# First of All, What's Load Balancing?
Load balancing is **the act of distributing a workload over several hosts**.
This is critical to allow applications to have a large number of users without overloading the server.
[[Content Delivery Network]]s often include load balancing features.
# How Does It Work?
In theory, you set a load balancer up in front of the servers you want to balance the traffic to.
You configure the load balancer to target the servers you'll spread the traffic on.
Then, as requests arrive at your load balancer, it will be able to spread the requests over the servers.
## How Does the Load Balancer Choose?
The load balancer chooses the server that will process a given request based on **a number of possible algorithms**.
These algorithms can be **either static or dynamic**.
## Static Load Balancing Algorithms
Static algorithms **distribute the traffic without actually checking the states of the servers**.
This means that they can't make informed decision based on which server is the least congested.
- [[Round Robin DNS]]
- Client-side random load balancing
## Dynamic Load Balancing Algorithms
Dynamic algorithms **know the state of their servers, and can distribute workloads accordingly**.
This has a drawback, however, which is that **configuring dynamic load balancers is more complicated**.
The tradeoff is worth it for large web applications and servers expecting much traffic.
# Resources
- [Cloudflare Article on Load Balancing](https://www.cloudflare.com/learning/performance/what-is-load-balancing/)