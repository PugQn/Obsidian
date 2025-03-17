*In Assignment 3 you will need to simulate a router- this tutorial covers a simplified version of this. A router reads packages from input ports and processes them in a specific order. Input ports are numbered 0...255. During each cycle, an arbitrary number of packages arrives at the input queues. The router then tries to read one package from each input port queue, in order (starting with port 0), and if available processes it. For clarity, one cycle consists of (a) reading any number of packets into input queues, and (b) processing one packet per input queue. Processing proceeds cycle by cycle, until no more inputs arrive and all input queues are empty (so that all packets have been processed).*

Need to traverse ports in order.

## Question 1
*What would be a sensible C++ data structure to store the packets coming in?*

use vector of vectors

## Question 2
*Is it necessary to store packets as (port, payload) pairs??*
No need to store port numbers if vector it is stored in represents the port

## Question 3
*What would be a sensible data structure to store the processing order?*

Vectors are not so good as removing the first one will require all others to shuffle forwards.
Can use a ring buffer - vector with wrap around - limited space tho.... grow or shrink the vector as needed. resize at specified time.

A queue would be better
implement using a linked list is better - used with pointers at both ends, insert at end, remove from beginning


## Question 4
*In which order do packets from the following input get processed?*
Cycle 1: *2 2 ports 2 for*
Cycle 2: *2 2 order 1 matter*


Cycle 1:
QUEUES
Port1: 
Port2: ports, for
OUTPUTS
Port1: 
Port2: ports
Port1: 
Port2: for

Cycle 2:
QUEUES
Port1: matter
Port2: order
OUTPUTS
Port1: matter
Port2: order


Need to learn more about vectors. How are they resized? What triggers their growth/shrinkage?