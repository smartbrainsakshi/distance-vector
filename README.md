
# Distance-Vector-Routing-and-Flow-Control-Simulator

  

The project simulates a network traffic in a given topology where the distance vector algorithm is used for path computations and routing. The topology of the network is given and cannot be changed by the user. User can change the path costs between each router, and specify any number of flows from any router to the other. Package size also can be changed. After the user specifies, the program can run the network traffic.

  

The program basically consists of two major parts:

- Distance Vector Computation

- Forwarding and Routing Algorithm

  

*Distance Vector Computation:*

In this part, the user enters the path costs, and the distance vectors are computed by the program, and exported to a text file.

  

*Flow Routing Algorithm:*

In this part, the program takes the output of first part, the distance vectors, as an input to construct the topology. The user enters each packet flow to be executed, i.e., specifies the packages to be transmitted from which router to which router with the sizes of packages. Then, the program simulates the traffic at each steps of each packages including visited routers, queues, delays etc.

  

Used skills:

* Socket programming in router communications

* Multi-Threading

* De-centralized programming

* Object-oriented design

* I/O Management, File Reading/Writing

* Implementation of Distance Vector, Routing/Forwarding, and Flow Control Algorithms

  

**Sample Outputs**
1. ***Executing Distance Vector Computation.***

![](https://github.com/DenizKrdy98/Distance-Vector-Routing-and-Flow-Control-Simulator/blob/main/topology.png)

```sh
Simulation converged.
PRINTING PATHS FROM 0 TO 0
[] cost = 0
PRINTING PATHS FROM 0 TO 1
[0] cost = 5
[0, 2] cost = 12
[0, 2, 3, 4] cost = 14
PRINTING PATHS FROM 0 TO 2
[0, 1] cost = 14
[0, 1, 4, 3] cost = 16
[0] cost = 3
PRINTING PATHS FROM 0 TO 3
[0, 1, 2] cost = 17
[0, 1, 4] cost = 13
[0, 2, 1, 4] cost = 20
[0, 2] cost = 6
PRINTING PATHS FROM 0 TO 4
[0, 1, 2, 3] cost = 24
[0, 1] cost = 6
[0, 2, 1] cost = 13
[0, 2, 3] cost = 13
PRINTING PATHS FROM 1 TO 0
[1] cost = 5
[1, 2] cost = 12
[1, 4, 3, 2] cost = 14
PRINTING PATHS FROM 1 TO 1
[] cost = 0
PRINTING PATHS FROM 1 TO 2
[1, 0] cost = 8
[1] cost = 9
[1, 4, 3] cost = 11
PRINTING PATHS FROM 1 TO 3
[1, 0, 2] cost = 11
[1, 2] cost = 12
[1, 4] cost = 8
PRINTING PATHS FROM 1 TO 4
[1, 0, 2, 3] cost = 18
[1, 2, 3] cost = 19
[1] cost = 1
PRINTING PATHS FROM 2 TO 0
[2] cost = 3
[2, 1] cost = 14
[2, 3, 4, 1] cost = 16
PRINTING PATHS FROM 2 TO 1
[2, 0] cost = 8
[2] cost = 9
[2, 3, 4] cost = 11
PRINTING PATHS FROM 2 TO 2
[] cost = 0
PRINTING PATHS FROM 2 TO 3
[2, 0, 1, 4] cost = 16
[2, 1, 4] cost = 17
[2] cost = 3
PRINTING PATHS FROM 2 TO 4
[2, 0, 1] cost = 9
[2, 1] cost = 10
[2, 3] cost = 10
PRINTING PATHS FROM 3 TO 0
[3, 2] cost = 6
[3, 2, 1] cost = 17
[3, 4, 1] cost = 13
[3, 4, 1, 2] cost = 20
PRINTING PATHS FROM 3 TO 1
[3, 2, 0] cost = 11
[3, 2] cost = 12
[3, 4] cost = 8
PRINTING PATHS FROM 3 TO 2
[3] cost = 3
[3, 4, 1, 0] cost = 16
[3, 4, 1] cost = 17
PRINTING PATHS FROM 3 TO 3
[] cost = 0
PRINTING PATHS FROM 3 TO 4
[3, 2, 0, 1] cost = 12
[3, 2, 1] cost = 13
[3] cost = 7
PRINTING PATHS FROM 4 TO 0
[4, 1] cost = 6
[4, 1, 2] cost = 13
[4, 3, 2] cost = 13
[4, 3, 2, 1] cost = 24
PRINTING PATHS FROM 4 TO 1
[4] cost = 1
[4, 3, 2, 0] cost = 18
[4, 3, 2] cost = 19
PRINTING PATHS FROM 4 TO 2
[4, 1, 0] cost = 9
[4, 1] cost = 10
[4, 3] cost = 10
PRINTING PATHS FROM 4 TO 3
[4, 1, 0, 2] cost = 12
[4, 1, 2] cost = 13
[4] cost = 7
PRINTING PATHS FROM 4 TO 4
[] cost = 0
{1=1=2, 2=2=1, 3=2=1, 4=1=2}
{0=0=2, 2=0=2, 3=4=0, 4=4=0}
{0=0=1, 1=0=1, 3=3=0, 4=0=1}
{0=2=4, 1=4=2, 2=2=4, 4=4=2}
{0=1=3, 1=1=3, 2=1=3, 3=3=1}
```


2. ***Executing FlowRouting.java***


```sh

*************************** PROGRAM INITIALIZATION ***************************

Flows are read from "flows.txt":

f0: 2,4,200 -> Source Node: 2, Destination Node: 4, Data Size: 200.0, Priority: 0

f1: 3,0,150 -> Source Node: 3, Destination Node: 0, Data Size: 150.0, Priority: 1

f2: 3,1,200 -> Source Node: 3, Destination Node: 1, Data Size: 200.0, Priority: 2

f3: 3,0,150 -> Source Node: 3, Destination Node: 0, Data Size: 150.0, Priority: 3

  

Forwarding Table is read from "forwardingTable.txt":

{1=1=2, 2=2=1, 3=2=1, 4=1=2}

{0=0=2, 2=0=2, 3=4=0, 4=4=0}

{0=0=1, 1=0=1, 3=3=0, 4=0=1}

{0=2=4, 1=4=2, 2=2=4, 4=4=2}

{0=1=3, 1=1=3, 2=1=3, 3=3=1}

  

Topology is constructed by using bandwidth and forwarding table info.

Link (0-1) -> BW: 10.0, Availability(0/1): 1.0, Reserved Until Time: 0.0

Link (0-2) -> BW: 15.0, Availability(0/1): 1.0, Reserved Until Time: 0.0

Link (1-2) -> BW: 5.0, Availability(0/1): 1.0, Reserved Until Time: 0.0

Link (1-4) -> BW: 15.0, Availability(0/1): 1.0, Reserved Until Time: 0.0

Link (2-3) -> BW: 10.0, Availability(0/1): 1.0, Reserved Until Time: 0.0

Link (3-4) -> BW: 5.0, Availability(0/1): 1.0, Reserved Until Time: 0.0

  
  

****************************** FLOW ROUTING **********************************

  

TIME is 0.0

--------------------------------------------------------------

-> Completion Status of Flows: [false, false, false, false]

Process For f0:

*f0: path added.

*f0's path is done. Transmission will be completed at action time.

*f0's added sub-path: [2, 0, 1, 4]

*f0's action time is 20.0

*f0's so-far total path: [2, 0, 1, 4]

Process For f1:

*f1: prevented from a loop.

*f1: path added.

*f1 will be queued after having a sub-path.

*f1's sub-path transmission lasts longer than the queue time. Action time is considered as queue time.

*f1's added sub-path: [3, 2, 1]

*f1's action time is 20.0

*f1's so-far total path: [3, 2, 1]

Process For f2:

*f2: prevented from a loop.

*f2: path added.

*f2 will be queued after having a sub-path.

*f2's sub-path transmission lasts longer than the queue time. Action time is considered as queue time.

*f2's added sub-path: [3, 4]

*f2's action time is 20.0

*f2's so-far total path: [3, 4]

Process For f3:

*f3: queued.

*f3: queued at the initial.

*f3's action time is 20.0

*f3's so-far total path: [3]

  

TIME is 20.0

--------------------------------------------------------------

-> Completion Status of Flows: [false, false, false, false]

Done, not proceeded. f0

Process For f1:

*f1: path added.

*f1's path is done. Transmission will be completed at action time.

*f1's added sub-path: [1, 0]

*f1's action time is 30.0

*f1's so-far total path: [3, 2, 1, 0]

Process For f2:

*f2: path added.

*f2's path is done. Transmission will be completed at action time.

*f2's added sub-path: [4, 1]

*f2's action time is 40.0

*f2's so-far total path: [3, 4, 1]

Process For f3:

*f3: path added.

*f3's path is done. Transmission will be completed at action time.

*f3's added sub-path: [3, 2, 0]

*f3's action time is 35.0

*f3's so-far total path: [3, 2, 0]

  

TIME is 30.0

--------------------------------------------------------------

-> Completion Status of Flows: [true, false, false, false]

Done, not proceeded. f0

Done, not proceeded. f1

Action time is waited. f2

Action time is waited. f3

  

TIME is 35.0

--------------------------------------------------------------

-> Completion Status of Flows: [true, true, false, false]

Done, not proceeded. f0

Done, not proceeded. f1

Action time is waited. f2

Done, not proceeded. f3

  

TIME is 40.0

--------------------------------------------------------------

-> Completion Status of Flows: [true, true, false, true]

Done, not proceeded. f0

Done, not proceeded. f1

Done, not proceeded. f2

Done, not proceeded. f3

  

*** END: TIME IS 40.0

--------------------------------------------------------------

Completion Status of Flows: [true, true, true, true]

Flow Routing has done successfully at time = 40.0.

f0's final path: [2, 0, 1, 4], done at time = 20.0.

f1's final path: [3, 2, 1, 0], done at time = 30.0.

f2's final path: [3, 4, 1], done at time = 40.0.

f3's final path: [3, 2, 0], done at time = 35.0.

  

```