## 4. Solution Concept

# Current Architecture:

UMass Amherst owns several racks of servers which they access through CloudLab which is a software that manage those resources. This also makes these shared resources available to other CloudLab users and allows them to interconnect them with other CloudLab data centers. Similary, Boston University and Northeastern University have a set of racks which they share between themselves through ESI which is a similar software that provides this management service.

To access a resource across these universities is a challenging task that involves sharing of sensitve information which is not ideal. Therefore, we propose a solution to build bring all the resources from all the three universities under a common umbrella for shared access of resources. This can be achieved by allowing all three universities to use CLoudlab as the common provider which would work on top of ESI. In doing so, CloudLab would become an ESI user that will be granted the permission to use the resources for the duration of the lease for the experiment.

**Cloudlab on ESI Architecture** 

Below is a description of the system components that are building blocks of the architectural design:

* CloudLab: A management framework designed for researchers to run experiments on customizable cloud infrastructure.

* ESI: A service allowing multiple tenants to flexibly allocate baremetal machines from a pool of available hardware, create networks, attach baremetal nodes and networks, and to optionally provision an operating system.

* Multiple baremetal machines managed by the three universities.


![Cloudlab on ESI Architecture](https://user-images.githubusercontent.com/60124910/134443639-f8aeba2b-f611-4e33-aeb8-d72ee4f4cc01.png)


Key design decisions and motivation behind them.

This section discusses the implications and reasons of the design decisions made during the global architecture design.
