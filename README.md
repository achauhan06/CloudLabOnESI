## 4. Solution Concept

**Current Architecture**

UMass Amherst owns several racks of servers that they access through CloudLab, which is software that manages those resources. This also makes these shared resources available to other CloudLab users and allows them to interconnect with other CloudLab data centers. Similarly, Boston University and Northeastern University have a set of racks that they share between themselves through ESI which is similar software that provides this management service.

To access a resource across these universities is a challenging task that involves sharing sensitive information which is not ideal. Therefore, we propose a solution to bring all the resources from all three universities under a common umbrella for shared access to resources. This can be achieved by allowing all three universities to use CloudLab as the common provider which would work on top of ESI. In doing so, CloudLab would become an ESI user that will be granted permission to use the resources for the duration of the lease for the experiment.

**CloudLab on ESI Architecture** 

Below is a description of the system components that are the building blocks of the architectural design:

* CloudLab: A management framework designed for researchers to run experiments on customizable cloud infrastructure.

* ESI: A service allowing multiple tenants to flexibly allocate bare-metal machines from a pool of available hardware, create networks, attach bare-metal nodes and networks, and optionally provision an operating system.

* Multiple bare-metal machines managed by the three universities.


![Cloudlab on ESI Architecture](https://user-images.githubusercontent.com/60124910/134443639-f8aeba2b-f611-4e33-aeb8-d72ee4f4cc01.png)


Key design decisions and motivation behind them.

Following are the steps to make CloudLab the common platform across all the universities to provision resources and make ESI the middle layer for managing all the bare-metal machines:

* Changing ESI configurations: This will make it the common point of control under which the complete OCT rack resides. 

* Signaling between ESI and CloudLab: Whenever resources are no longer being utilized, CloudLab should signal back to ESI so that these resources can be made available to ESI for putting them back in the pool of unassigned resources.

Above mentioned changes require the following steps:

* Step 1: Identification of the commands that are invoked by CloudLab for all the management operations.
* Step 2: Identification of suitable ESI commands that can be used as a replacement.
* Step 3: Implementation of these calls in the CloudLab code.
