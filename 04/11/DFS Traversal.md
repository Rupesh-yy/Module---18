## DFS Traversal
## AIM
To write a Python program to perform Depth First Search (DFS) traversal on a directed graph starting from a given source vertex using the recursive DFSUTIL function.
## ALGORITHM
Step 1:
Create a graph using an adjacency list representation.
Step 2:
  Define the function DFSUtil(v, visited) which:
  Marks the current vertex v as visited.
  Prints the vertex.
  Recursively visits all unvisited adjacent vertices.
Step 3:
  In the DFS(start_vertex) function:
  Create an empty set visited to store visited vertices.
  Call DFSUtil(start_vertex, visited).
Step 4:
Add all directed edges to form the graph shown in the diagram.
Step 5:
Input a starting vertex from the user.
Step 6:
Invoke the DFS function to print the DFS traversal from the given source vertex.
Step 7:
End.

## PROGRAM
```
# Python3 program to print DFS traversal
# from a given graph
from collections import defaultdict

# This class represents a directed graph using
# adjacency list representation


class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# A function used by DFS
	def DFSUtil(self, v, visited):

		#Mark the current node as visited
		# and print it
		visited.add(v)
		print(v,end=' ')
		for neighbour in self.graph[v]:
		    if neighbour not in visited:
		        self.DFSUtil(neighbour,visited)
		
		
	# The function to do DFS traversal. It uses
	# recursive DFSUtil()
	def DFS(self, v):

		# Create a set to store visited vertices
		visited = set()

		# Call the recursive helper function
		# to print DFS traversal
		self.DFSUtil(v, visited)

# Driver code


# Create a graph given
# in the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print("Following is DFS from (starting from vertex {})".format(n))
g.DFS(n)



```
## OUTPUT
<img width="770" height="195" alt="image" src="https://github.com/user-attachments/assets/48a10ffa-d341-4e6c-b04f-1b7089dc7ee7" />

## RESULT
Thus, the Depth First Search (DFS) traversal starting from the given source vertex is successfully generated.
