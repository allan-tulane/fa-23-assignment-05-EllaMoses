# CMPS 2200 Assignment 5
## Answers

**Name:** Ella Moses






- **1a.**
The heap and shape properties are maintained so the height of a d-nary tree is $log_d(n)$ where n is the number of nodes

- **1b.**
The insert operation is dependent on the height of the tree so the work is 
$O(log_d(n))$. The number of children each node has does not effect insert. Delete min does depend on the number of children each node has because the parent must be compared to its children so the work of 
delete min is $O(dlog_d(n))$.
- **1c.**
The work of insert is equal to $O(log_d(n))$ and the work of delete min is equal to $O(dlog_d(n))$. Insert may be called E times and delete min may be called V times. Since the dict operations are in constant time (same as with binary heap) the work is dominated by the work of insert and delete min so the total work is equal to $O((E+Vd)log_d(V))$

- **1d.**
To balance the insert and delete min operators we want to set d=E/V 

- **2a.**
Initialize all values to infinity, then update as shortest path can be found. <br>
Distance between 0 and 0 is 0, only need node 0 so update k=0,1,2:
APSP(0,0,0)= 0
APSP(0,0,1)= 0
APSP(0,0,2)= 0 <br>
Distance between 1 and 1 is 0, need access to node 1 so update k=1,2:
APSP(1,1,0)= inf
APSP(1,1,1)= 0
APSP(1,1,2)= 0 <br>
Distance between 2 and 2 is 0, need access to node 2 so update k=2:
APSP(2,2,0)= inf
APSP(2,2,1)= inf
APSP(2,2,2)= 0 <br>
Need access to nodes at least 0,1 so update for k=1,2:
APSP(0,1,0)= inf
APSP(0,1,1)= -2
APSP(0,1,2)= -2 <br>
Need access to nodes at least 0,2 so update for k=2:
APSP(0,2,0)= inf
APSP(0,2,1)= inf
APSP(0,2,2)= -1 <br>
Need access to nodes at least 1,2 so update for k=2:
APSP(1,2,0)= inf
APSP(1,2,1)= inf
APSP(1,2,2)= 0

- **2b.**
APSP(i,j,2) is more accurate than APSP(i,j,1) because we are allowed to use all vertices, when we aren't allowed to use all vertices, some connections can't be made so their value remains at inf. APSP(i,j,2) can't be written in terms of APSP(i,j,0) and APSP(i,j,1). For example: APSP(1,2,0)= inf, APSP(1,2,1)= inf
APSP(1,2,2)= 0. In this case we know that APSP(1,2,2) will be the shortest path because the previous 2 are inf, but we can't predict the value. 

- **2c.**
The optimal substructure property would say that if the shortest path between has an intermediate vertex, then the shortest path would contain the shortest path between the starting vertex and intermediate vertex. 

- **2d.**
Let d be the number of possible vertex pairs. For each vertex pair, E new distances needs to be computed and the distances of the subproblems can be used in all other cases. number of possible pairs is equal to (V choose 2) + V. V choose 2 = V!/(2*(V-2)!)
let V choose 2 equal d. Overall work is O(E(d+V))

- **2e.**
work of johnsons is O(VElogE). This is better than the work above. 


- **3a.**
Yes, because of the light-edge property which states that For any cut of
G, the minimum weight edge that crosses the cut is contained in the minimum spanning tree of
G. This means that while selecting the MST, the maximum weights are also be minimized becuase the smallest edge weights in the cycle are selected. 
 

- **3b.**
The first and second best MST will only differ by 1 edge. This means that we can calculate second best MST without each edge in the MST. For each edge in the MST remove it from the list of possible edges and then compute the MST using all the remaining edges. The best one will be the second best overall.

- **3c.**
The work of this will be equal to the work of finding the best tree V times (1 time to find best MST and V-1 times to compute all possibilites for second best) So, the final work is O(VElogE)