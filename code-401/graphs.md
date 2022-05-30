# Implementation: Graphs

To turn in your reading “Reply” to this discussion by teaching something that you learned. Then review what one of your classmates learned, and leave a comment.

Some ideas for how you might want to teach:

-   Use an analogy
-   Explain a detail in depth
-   Use WHY, WHAT, HOW structure
-   Tutorial / walk through an example
-   Write a quiz
-   Create a vocabulary/definition list
-   Write a cheat sheet
-   Create a diagram / visualization / cartoon of a topic
-   Anthropomorphize the concepts, and write a conversation between them
-   Build a map of the information
-   Construct a fill-in-the-blank worksheet for the topic

## Resources

-   Read: [Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)

### Graphs
Graphs are a non-linear data structure that can be looked at as a collection of vertices (nodes!) potentially connected by line segments, referred to as "edges"

**Terminology** 
1. *Vertex*: Vertex, also called a node, is a data object that can have zero or more adjacent vertices
2. *Edge*: Connection between two nodes
3. *Neighbor*: the neighbors of a node are it's adjacent nodes, connected via an edge
4. *Degree*: the degree of a certex is the number of edges connected to that vertex 

**Directed Vs Undirected**  
*Undirected Graph* is when the graph edge is undirected or bi-directional, meaning that the undirected graph doesn't move in any direction.   
*Directed Graph* also called a *Digraph* is where every edge is directed. Meaning it has a direction, and each node is directed at another node. There is a specific requirement of what node should reference the next.   

**Complete vs Connected vs Disconnected**  
*Complete Graph* is where all the nodes are connected to all other nodes  
*Connected Graph* is where the all nodes have at least one edge  
*Disconnected Graph* Is where some nodes don't have edges  

**Acyclic vs Cyclic**  
*Acyclic Graph* is directed graph without cycles. Where a cycle is when a node can be traversed through and potentially end up back at itself.   
*Cyclic Graph* is a grpah that has cycles, defined as a path of positive length that starts and ends at the same node.  

**Graph Representation**
We present graphs in two ways  
Using this Graph as an example:   
![Example](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)
1. *Adjacency Matrix*
	1. ![Adjacency Matrix](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjMatrix.PNG)
2. *Adjacency List*
	1. ![Adjacency List](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjList.PNG)

**Weighted Graphs**  
A weighted graph is a graph with numbers assigned to it's edges.  
The numbers are called weights.  

**Traversals**  
* *Breadth First* start at a specified node, then visit all the nodes that are closest to the root as possible, then from there you traverse outwards, level by level. 
* *Depth First* Where the algorithm is:
	*  Push the root node into a stack  and mark as visited
	* start a while loop that runs as long as the stack is not empty
	* Pop the top node off the stack and check it's neighbors
	* If the neighbor hasn't been visited then push it onto the stack and mark as visited 
	* repeat until stack is empty and all nodes have been visited. 

**Real World Uses of Graphs** 
1. GPS and Mapping
2. Driving Directions
3. Social Networks
4. Airline traffic
5. Netflix's generation of suggestions. 
