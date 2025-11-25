## TOPOLOGICAL SORT
## AIM
To write a Python program that performs Topological Sorting on a Directed Acyclic Graph (DAG) using Depth-First Search (DFS) and prints the vertices in topologically sorted order.

## ALGORITHM
Step 1:
Initialize the number of vertices V, adjacency list adj, a visited list visited, and a departure list departure to store finishing times of vertices.

Step 2:
Define a function addEdge(u, v) to add a directed edge from vertex u to vertex v in the adjacency list.

Step 3:
  *Define the DFS function DFS(v):
  *Mark vertex v as visited.
  *Recursively call DFS on all unvisited adjacent vertices.
  *After exploring all neighbors, store vertex v in the departure list using a global time counter.
  *Increment the time.

Step 4:

*Define the topologicalSort() function:
  *For every vertex from 0 to V-1:
    *If not visited, call DFS(i).
    *After DFS completes for all vertices, print the vertices from departure[V-1] to departure[0] (reverse departure order), which gives the topological order.

Step 5:
Create the graph using the given edges:
  
  5 → 2
  5 → 0
  4 → 0
  4 → 1
  2 → 3
  3 → 1
  
Step 6:

Call the topological sort function to print the result.

Step 7:

End.

## PROGRAM
```
# A Python3 program to print topological sorting of a DAG
def addEdge(u, v):
	global adj
	adj[u].append(v)

# The function to do DFS() and stores departure time
# of all vertex
def DFS(v):
	global visited, departure, time
	visited[v] = 1
	for i in adj[v]:
		if visited[i] == 0:
			DFS(i)
	departure[time] = v
	time += 1

# The function to do Topological Sort. It uses DFS().
def topologicalSort():

#.....
    for i in range(V):
        if (visited[i]==0):
            DFS(i)
    for i in range(V-1,-1,-1):
        print(departure[i],end=" ")

#.....





# Driver code
if __name__ == '__main__':

	# Create a graph given in the above diagram
	V,time, adj, visited, departure = 6, 0, [[] for i in range(7)], [0 for i in range(7)],[-1 for i in range(7)]
	addEdge(5, 2)
	addEdge(5, 0)
	addEdge(4, 0)
	addEdge(4, 1)
	addEdge(2, 3)
	addEdge(3, 1)

	print("Topological Sort of the given graph is")
	topologicalSort()


```
## OUTPUT
<img width="766" height="186" alt="image" src="https://github.com/user-attachments/assets/a62507f9-4253-432e-9df6-af092b0c4b2a" />

## RESULT
Thus, a valid topological order for the given graph is successfully generated.
