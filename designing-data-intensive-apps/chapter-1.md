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

![image](https://github.com/shartrooper/learning-sources-pickups/assets/21326996/0e649dd1-34ac-4ab3-9018-3e4c894ef0ba)

* __AMAZON EXAMPLE__: It’s important to keep those customers happy by ensuring the website is fast
for them: Amazon has also observed that a 100 ms increase in response time reduces
sales by 1%, and others report that a 1-second slowdown reduces a customer sat‐
isfaction metric by 16%.

* __Percentiles in Practice__:
High percentiles become especially important in backend services that are called mul‐
tiple times as part of serving a single end-user request. Even if you make the calls in
parallel, the end-user request still needs to wait for the slowest of the parallel calls to
complete. It takes just one slow call to make the entire end-user request slow, as illus‐
trated in Figure 1-5. Even if only a small percentage of backend calls are slow, the
chance of getting a slow call increases if an end-user request requires multiple back‐
end calls, and so a higher proportion of end-user requests end up being slow (an
effect known as tail latency amplification).
If you want to add response time percentiles to the monitoring dashboards for your
services, you need to efficiently calculate them on an ongoing basis. For example, you
may want to keep a rolling window of response times of requests in the last 10
minutes. Every minute, you calculate the median and various percentiles over the val‐
ues in that window and plot those metrics on a graph.
The naïve implementation is to keep a list of response times for all requests within the
time window and to sort that list every minute. If that is too inefficient for you, there
are algorithms that can calculate a good approximation of percentiles at minimal
CPU and memory cost, such as forward decay, t-digest, or HdrHistogram
. Beware that averaging percentiles, e.g., to reduce the time resolution or to com‐
bine data from several machines, is mathematically meaningless—the right way of
aggregating response time data is to add the histograms.

* The architecture of systems that operate at large scale is usually highly specific to the
application—there is no such thing as a generic, one-size-fits-all scalable architecture
(informally known as magic scaling sauce). The problem may be the volume of reads,
the volume of writes, the volume of data to store, the complexity of the data, the
response time requirements, the access patterns, or (usually) some mixture of all of
these plus many more issues.

## MAINTAINABILITY


