## BFS TRAVERSAL
## AIM
To write a Python program that performs Breadth First Search (BFS) traversal on a directed graph starting from a given source vertex and prints all reachable vertices in BFS order.
## ALGORITHM
1.Start
2.Create a list/array visited[] and mark all vertices as not visited.
3.Create an empty queue.
4.Mark the starting vertex s as visited, and enqueue it.
5.Repeat the following until the queue becomes empty:
  *Dequeue a vertex u
  *Print or store u
  *For each adjacent vertex v of u:
    *If v is not visited:
      *Mark v as visited
      *Enqueue v
6.End

## PROGRAM
```
# Python3 Program to print BFS traversal
# from a given source vertex. BFS(int s)
# traverses vertices reachable from s.
from collections import defaultdict

# This class represents a directed graph
# using adjacency list representation
class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self,u,v):
		self.graph[u].append(v)

	# Function to print a BFS of graph
	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True

		# Write the Complete BFS Function 
		while queue:
		    s=queue.pop(0)
		    print(s,end=" ")
		    for i in self.graph[s]:
		        if visited[i]==False:
		            queue.append(i)
		            visited[i]=True
		
		
		

# Create a graph given in
# the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print ("Following is Breadth First Traversal"
				" (starting from vertex {})".format(n))
g.BFS(n)

```
## OUTPUT
<img width="1265" height="280" alt="image" src="https://github.com/user-attachments/assets/f676f040-1614-481e-bbc0-6f7c39b42a76" />

## RESULT
Thus, the Breadth First Search (BFS) traversal starting from the given source vertex is successfully generated.
