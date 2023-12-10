# CMPS 2200 Assignment 5
## Answers

**Name:** Ella Moses






- **1a.**
The height of a complete d-nary tree is ceiling of log_d(n) where n is the number of nodes

- **1b.**
insert is O(log_d(n))
delete min is O(dlog_d(n))
in both cases n is number of nodes
- **1c.**
O(d^2log_d(n))

- **1d.**
d = 1

- **2a.**
APSP(0,0,0)= 0 
APSP(0,0,1)= 0
APSP(0,0,2)= 0
APSP(1,1,0)= inf
APSP(1,1,1)= 0
APSP(1,1,2)= 0
APSP(2,2,0)= inf
APSP(2,2,1)= inf
APSP(2,2,2)= 0
APSP(0,1,0)= inf
APSP(0,1,1)= -2
APSP(0,1,2)= -2
APSP(0,2,0)= inf
APSP(0,2,1)= inf
APSP(0,2,2)= -1
APSP(1,2,0)= inf
APSP(1,2,1)= inf
APSP(1,2,2)= 0
- **2b.**
APSP(i,j,1) <= APSP(i,j,2)

APSP(i,j,2) can't be written in terms of APSP(i,j,0) and APSP(i,j,1). For example: APSP(1,2,0)= inf
APSP(1,2,1)= inf
APSP(1,2,2)= 0

- **2c.**
The optimal subpath for a subproblem of the path is also included in the subproblem of the total path. 
- **2d.**
d*d!
resulting work is O(d*d!log_d(n))

- **2e.**
work of johnsons is O(VElogE). This is more optimal than above. 


- **3a.**
No, it is possible that the MMET will result in a greater total weight than the MST. For example, say there is a graph with source node A that connects to B with weight 2 and C with weight 1. MMET will choose C regardless of the reamining parts of the graph becuase it is trying to choose the minimum edge weight coming from A. If B connects to D with weight 1 and C connects to D with weight 6, MST would be ABD but MMET will be ACD. 

- **3b.**
The first and second best MST will only differ by 1 edge. This means that we can calculate the For each edge in the MST, remove it from the list of possible edges and then compute the MST using all the remaining edges. The best one will be the second best overall.

- **3c.**
The work of this will be equal to the work of finding the best tree V times (1 time to find best MST and V-1 times to compute all possibilites for second best) So, the final work is O(VElogE)