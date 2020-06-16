# Researcher-Collaboration-Graph-and-Maximum-Spanning-Tree-Algorithm

# Algorithm Analysis and Design Semester Project

## Project Guidelines:

DBLP listed more than 3.66 million journal articles, conference papers, and other
publications on computer science in July 2016, up from about 14,000 in 1995. All important
journals on computer science are tracked. Proceedings papers of many conferences are
also tracked. It is mirrored at three sites across the Internet.
This semester your Design and Analysis of Algorithm project is to use a DBLP dataset.

### Download the dataset
https://drive.google.com/file/d/1_-n6eQI-7O9l9F9tHteQAH_CRsqeeUfC/view?usp=sharing   

DBLP dataset has information of collaboration among multiple researchers. In this project
you have to find the most important collaboration among the whole dataset. In order to do
so you need to create a graph for the given data set. In your graph, Node represents
researchers and the link between them indicates collaboration among multiple researchers
while weight on that link shows the number of times those researchers have worked
together.    
Your tasks are following    
1. Create a graph representation from a file that has 3 columns, first two columns represent author id and third represents the weight of the link. Edge weight is proportional to the amount of collaboration (bigger means collaborating quite frequently)
2. Create a Maximum spanning tree from the graph created in (1) . This represents the top collaborators of each researcher.
3. By using the maximum spanning tree generated in (2) enumerate the top 5 distinct collaborator pairs. Your algorithm must perform better than brute force. Credit for this question mainly depends on the algorithm efficiency along with the accuracy.        
    
Instructions:    
● You need to submit your code in Google classroom.    
● This is a group project. Each group should not exceed more than 2.    
● Every group should notify TA’s about its members.    
● No late submissions are acceptable.    
● Code should be submitted with results. (Any language is allowed)    
● Assignment deadline is 15 May but in order to give enough time department have decided to give extension to project till 1 june and accept submissions without any deduction.    
● Considering COVID-19 situation in Pakistan IF there are no final exams in Pakistan then this project would have considerably high weightage.    

### Graph Implementation

Best data structures that we can use to implement graphs in python. They are none other than dictionaries and lists.

### Terminology
##### Vertex  
A vertex is the most basic part of a graph and it is also called a node. Throughout we'll call it note. A vertex may also have additional information and we'll call it as payload.

##### Edge    
An edge is another basic part of a graph, and it connects two vertices/ Edges may be one-way or two-way. If the edges in a graph are all one-way, the graph is a directed graph, or a digraph. The picture shown above is not a digraph.\n
  
##### Weight   
Edges may be weighted to show that there is a cost to go from one vertex to another. For example in a graph of roads that connect one city to another, the weight on the edge might represent the distance between the two cities or traffic status.

##### Graph   
A graph can be represented by G where G=(V,E). V is a set of vertices and E is a set of edges. Each edge is a tuple (v,w) where w,v in V. We can add a third component to the edge tuple to represent a weight. A subgraph s is a set of edges e and vertices v such that e in E and v in V.
    
    V={a,b,c,d,e,f}
    and the set of nine edges:
 
    E={(a,b,7),(a,c,9),(a,f,14),(b,d,15),(b,c,10),(c,d,11),(c,f,2),(d,e,6),(e,f,9)}
    
##### Path    
A path in a graph is a sequence of vertices that are connected by edges. We usually define a path as w_1, w_2,..., w_n such that (w_i, w_{i+1}) in E for all 1 le i le n-1. The unweighted path length is the number of edges in the path (n-1). The weighted path length is the sum of the weights of all the edges in the path. For example in the picture above, the path from a to e is the sequence of vertices (a, c, d, e). The edges are {(a, c, 9), (c, d, 11), (d, e, 6)}.
 
##### Cycle   
A cycle in a directed graph is a path that starts and ends at the same vertex. A graph with no cycles is called an acyclic graph. A directed graph with no cycles is called a directed acyclic graph or a DAG.

### Concept

Vertex class uses a dictionary (adjacent) to keep track of the vertices to which it is connected, and the weight of each edge. The Vertex constructor initializes the id, which is usually a string, and the adjacent dictionary. 

The add_neighbor() method is used add a connection from this vertex to another. 

The get_connections() method returns all of the vertices in the adjacency list. 

The get_weight() method returns the weight of the edge from this vertex to the vertex passed as a parameter.

The Graph class contains a dictionary(id-dict) that maps vertex names to vertex objects, and we can see the output by the __str__() method of Vertex class.

Graph also provides methods for adding vertices to a graph and connecting one vertex to another. 

The get_vertices() method returns the names of all of the vertices in the graph. 

The __iter__() method to make it easy to iterate over all the vertex objects in a particular graph. 

### We have our graph ready...... now moving forward towards the maximum spanning tree

A spanning tree of an undirected graph is a connected subgraph that covers all the graph nodes with the minimum possible number of edges. In general, a graph may have more than one spanning tree. If the graph is edge-weighted, we can define the weight of a spanning tree as the sum of the weights of all its edges. A maximum spanning tree has the largest weight among all spanning trees.

#### Pseudo-Code

If the number of nodes in a graph is V, then each of its spanning trees should have (V-1) edges and contain no cycles. We can describe Kruskal’s algorithm in the following pseudo-code to generate a maximum spanning tree:

1. Sort all the edges in non-decreasing order of their weight.
2. Pick the largest edge. Check if it forms a cycle with the spanning tree formed so far. If cycle is not formed, include this edge. Else, discard it.
3. Repeat 2. until there are (V-1) edges in the spanning tree.

##### What is Minimum Spanning Tree?
Given a connected and undirected graph, a spanning tree of that graph is a subgraph that is a tree and connects all the vertices together. A single graph can have many different spanning trees. A maximum spanning tree  for a weighted, connected and undirected graph is a spanning tree with weight greater than or equal to the weight of every other spanning tree. The weight of a spanning tree is the sum of weights given to each edge of the spanning tree.

##### How many edges does a maximum spanning tree has?
A maximum spanning tree has (V – 1) edges where V is the number of vertices in the given graph.

##### In simpler Words kya kerna hai ?
Step 1 – Remove all loops and parallel edges

Step 2 – Arrange all the edges in descending order of cost

Step 3 – Add edges with most weight
