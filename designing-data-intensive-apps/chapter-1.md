## Data-intensive applications fundamental ##  
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
