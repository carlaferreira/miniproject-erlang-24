# miniproject-erlang
# CPLT - Actor-based Concurrency Module

## Erlang Lab Class #2 - Miniproject

**Note that the mini-project is the same for the three modules (Go, Erlang, and Rust).** 

**DEADLINE** 29/11/2023 11:59AM

----
To submit your answers, simply push your files onto the repository. The problem will be graded.

----

## Resource Reservation System
* In a modern office building, a company's employees typically need to book or reserve the use of certain facilities in advance.
* Companies use automated systems to manage reservations of limited capacity resources in their facilities.
* The main design constraint for such a system is that reservations must be managed in such a way that no overbooking of a resource is ever allowed.
* In this mini-project, you will implement three variants of the resource reservation systems, offering slightly different features.
* Each variation must ensure that **no resource overbooking is possible** and that the system as a whole eventually makes progress.

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
