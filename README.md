# EX-2: Implement-Breadth-First-Search-Traversal-of-a-Graph

**Name:*Hariharan S*

**Register Number:*2305001009*

### Aim:
To Implement Breadth First Search Traversal of a Graph using Python 3.

### Theory:
Breadth-First Traversal (or Search) for a graph is like the Breadth-First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles so that we may come to the same node again. To avoid processing a node more than once, we divide the vertices into two categories:

Visited

Not Visited

A Boolean visited array is used to mark the visited vertices. For simplicity, it is assumed that all vertices are reachable from the starting vertex. BFS uses a queue data structure for traversal.

**How does BFS work?**
Starting from the root, all the nodes at a particular level are visited first, and then the next level nodes are traversed until all the nodes are visited. To do this, a queue is used. All the adjacent unvisited nodes of the current level are pushed into the queue, and the current-level nodes are marked visited and popped from the queue. Illustration: Let us understand the working of the algorithm with the help of the following example. 

### Algorithm:

step 1: Construct a Graph with Nodes and Edges

Step 2: Breadth First Uses Queue and iterates through the Queue for Traversal.

Step 3: Insert a Start Node into the Queue.

Step 4: Find its Successors Or neighbors and Check whether the node is visited or not.

Step 5: If Not Visited, add it to the Queue. Else Continue.

Step 6: Iterate steps 4 and 5 until all nodes get visited, and there are no more unvisited nodes.

### Program:
```
def bfs(graph, start):
    visited = []  
    queue = [start]  

    while queue:
        node = queue.pop(0)  
        if node not in visited:
            visited.append(node)  
            queue.extend(graph.get(node, []))  

    return visited

graph = {}
n = int(input("Enter number of nodes: "))  

for _ in range(n):
    node = input("Enter node: ")
    neighbors = input(f"Enter neighbors of {node} (comma separated): ").split(",")
    graph[node] = [neighbor.strip() for neighbor in neighbors]  

start_node = input("Enter the starting node for BFS: ")


print("BFS Traversal Order:", bfs(graph, start_node))
```
### Sample Input:

Enter number of nodes: 3

Enter node: A

Enter neighbors of A (comma separated): B

Enter node: B

Enter neighbors of B (comma separated): C

Enter node: C

Enter neighbors of C (comma separated): 

Enter the starting node for BFS: A

### Sample Output:

BFS Traversal Order: ['A', 'B', 'C']

### Input:
<img width="1060" height="580" alt="image" src="https://github.com/user-attachments/assets/c606d43d-94d9-4ec2-83a7-7d27f10545a3" />

### Output:
<img width="650" height="66" alt="image" src="https://github.com/user-attachments/assets/55964ef9-7405-4fc7-9257-f94bb6abfef0" />

### Result: 
The above Program executed successfully
