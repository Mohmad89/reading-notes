# Graphs 

* A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges

* Here is some common terminology used when working with Graphs: 
    1. Vertix (Node) : is a data object that can have zero or more adjacent vertices.
    2. Edge : connection between node.
    3. Neighbor  : The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
    4. Degree : number of Edge.

# Directed vs Undirected 

* Undirected Graph :is a graph where each edge is undirected or bi-directional ( ---- )
* Directed (Digraph ) : is a graph where every edge is directed. ( ---> )

# Complete vs Connected vs Disconnected 

* Complete Graph : is evry nodes are connected to all other node .
* Connected : evrt node in graph has at least one edge .
* Disconnected : some node may not have edges .

# Acyclic vs Cyclic

* Acyclic Graph : Directe graph without cycles .
* Cyclic Graphs : graph has cycle (graph that start and end at the same vertix(node)).

# Graph Representation

1. Adjacency Matrix : we use the metrix to represent it wiht use 2-dimensional array with put 0 if there's not any edge between node and 1 if there's edge between node.

2. Adjacency List : An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.

## Weighted Graphs 

* A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights. This is what a weighted graph looks like:
* we can assigne the weighte from 2D Array.

## Traversals

* You will be required to traverse through a graph. The traversals itself are like those of trees. Below is a breakdown of how you would traverse a graph.

1. Breadth First : In a breadth first traversal, you are starting at a specific vertex/node. This node must be specified when calling the BreadthFirst() method.

* Here is what the algorithm breadth first traversal looks like: 
    1. Enqueue the declared start node into the Queue.
    2. Create a loop that will run while the node still has nodes present.
    3. Dequeue the first node from the queue
    4. if the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.

2. Depth First : use the stack to push() the root after that will pop() the root then push() all child for this root.

## Real World Uses of Graphs

1. GPS and Mapping 
2. Driing Directions 
3. Social Networks
4. Airline Traffic
5. Netflix uses graphs for suggestions of products .