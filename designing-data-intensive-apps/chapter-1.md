![image](https://github.com/shartrooper/learning-sources-pickups/assets/21326996/23b83ca2-3659-4ff0-ab6d-5c04afd76495)## Data-intensive applications fundamental ##  
Typically built from standard building blocks that provide commonly needed functionality. For example, many applications need to:
* Store data so that they, or another application, can find it again later (databases)
* Remember the result of an expensive operation, to speed up reads (caches)
* Allow users to search data by keyword or filter it in various ways (search indexes)
* Send a message to another process, to be handled asynchronously (stream pro‐
cessing)
* Periodically crunch a large amount of accumulated data (batch processing)

![image](https://github.com/shartrooper/learning-sources-pickups/assets/21326996/a42ab246-598e-4519-9a8e-643381f2ee8c)

## RELIABILITY
* It can tolerate the user making mistakes or using the software in unexpected
ways.
* Its performance is good enough for the required use case, under the expected
load and data volume.
* The system prevents any unauthorized access and abuse

A fault is usually defined as __one component of the system deviating from its spec__, whereas a failure is when the system as a
whole __stops providing the required service to the user.__

There are situations in which we may choose to sacrifice reliability in order to reduce
development cost (e.g., when developing a prototype product for an unproven mar‐
ket) or operational cost (e.g., for a service with a very narrow profit margin)—but we
should be very conscious of when we are cutting corners. 

## SCALABILITY

* Scalability means considering questions like “If the system grows in a particular way,
what are our options for coping with the growth?” and “How can we add computing
resources to handle the additional load?”

* First, we need to succinctly describe the current load on the system; only then can we
discuss growth questions (what happens if our load doubles?). Load can be described
with a few numbers which we call load parameters. The best choice of parameters
depends on the architecture of your system: it may be requests per second to a web
server, the ratio of reads to writes in a database, the number of simultaneously active
users in a chat room, the hit rate on a cache, or something else. Perhaps the average
case is what matters for you, or perhaps your bottleneck is dominated by a small
number of extreme cases.

* The best choice of parameters
Depends on the architecture of your system: it may be requests per second to a web
server, the ratio of reads to writes in a database, the number of simultaneously active
users in a chat room, the hit rate on a cache, or something else.


![image](https://github.com/shartrooper/learning-sources-pickups/assets/21326996/e0f5200d-b25b-46c3-91e3-e06319a20028)

## Describing perfomance

* Once you have described the load on your system, you can investigate what happens
when the load increases. You can look at it in two ways:
- When you increase a load parameter and keep the system resources (CPU, mem‐
ory, network bandwidth, etc.) unchanged, how is the performance of your system
affected?
- When you increase a load parameter, how much do you need to increase the
resources if you want to keep performance unchanged?


