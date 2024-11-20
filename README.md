# miniproject-erlang
# PCLT - Actor-based Concurrency Module

## Erlang Lab Class #2 - Miniproject

**Note that the mini-project is the same for the three modules (Go, Erlang, and Rust).** 

**DEADLINE** 27/11/2024 23:59

----
To submit your answers, simply push your files onto the repository. The problem will be graded.

----

## Product Distribution System
The goal of this mini-project is to design and implement a concurrent product distribution system using Erlang’s process-based concurrency model. The system will simulate a factory that handles the shipment of products to clients using a fleet of trucks and multiple conveyor belts.

### General Requirements
	* Concurrency: The system must use independent Erlang processes to model conveyor belts and trucks.
	* Deadlock-Free: Ensure the absence of deadlocks; all packages must eventually be loaded onto trucks.
	* Progress Guarantee: All parts of the system must keep working to process and deliver packages.
	* Message Passing: Use Erlang’s message-passing mechanisms for synchronization and coordination.


### Task 1
* Implement the core resource reservation system.
* Must account for multiple clients interacting with the system concurrently.
* Must allow the system to concurrently book non-conflicting reservations.
* Multiple types of resources (e.g. meeting rooms, projectors, and teleconference systems) with different (non-zero) availabilities and concurrently running clients.
* Reservations must also have a timeframe and your system should simulate some sort of running clock that advances continuously.
* You may assume that users release resources automatically (i.e., you need not wait for a notification from a user to signal that a booked resource is now available).

**Note:** Add a small report to the task 1 folder that explains what correctness properties your system has and what achieves them.

### Task 2
* Extension of Task 1 to include **VIP Users**.
* VIP users have priority over regular users when booking a resource.
* Any resource that has been booked by a regular user, provided the booking is not yet in effect, can be overridden by a VIP user (i.e., a VIP can take over any booking that is still in the future).
* Regular users must be notified if their bookings are canceled due to a VIP user.
* VIPs cannot override other VIPs.

**Note:** Add a small report to the task 2 folder that explains what correctness properties your system has and what achieves them.

### Task 3
* Extension of Task 2 to include **compound reservations**.
* A user may attempt to book several resources simultaneously and the reservation as a whole can only succeed if all resources are booked.
* If at least one of the resources is unavailable, then the booking fails and no resource is assigned to the user because of this booking.
* For a lower grade, build on top of **Task 1**.

**Note:** Add a small report to the task 3 folder that explains what correctness properties your system has and what achieves them.
