## ADJANCENCY LIST OF REPRESENTATION OF GRAPH
## AIM
To write a Python program that demonstrates the adjacency list representation of an undirected graph and prints the adjacency list for every vertex.
## ALGORITHM
1.Start
2.Create a class AdjNode
  *Stores a vertex value.
  *Contains a pointer next to the next adjacent node in the list.
3.Create a class Graph
  *Initialize the number of vertices V.
  *Create an array graph of size V, each entry initially None.    
4.Define add_edge(src, dest)
  *Create a node for dest and insert it at the beginning of src’s adjacency list.
  *Create a node for src and insert it at the beginning of dest’s adjacency list (because the graph is undirected).
5.Define print_graph()
  *For each vertex i:
    *Print "Adjacency list of vertex i".
    *Start from graph[i] and traverse using next pointers.
    *Print every connected vertex.
6.In the main program
  *Create a graph with 5 vertices.
  *Add edges as given in the diagram.
  *Call print_graph() to display adjacency lists.
7.End

## PROGRAM
```
"""
A Python program to demonstrate the adjacency
list representation of the graph
"""

# A class to represent the adjacency list of the node


class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None


# A class to represent a graph. A graph
# is the list of the adjacency lists.
# Size of the array will be the no. of the
# vertices "V"
class Graph:
	def __init__(self, vertices):
		self.V = vertices
		self.graph = [None] * self.V

	# Function to add an edge in an undirected graph
	def add_edge(self, src, dest):
		# Adding the node to the source node
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node

		# Adding the source node to the destination as
		# it is the undirected graph
		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	
	def print_graph(self):
	    for i in range(self.V):
	        print(f"Adjacency list of vertex {i}\n head",end="")
	        temp=self.graph[i]
	        while temp:
	            print(f" -> {temp.vertex}",end="")
	            temp=temp.next
	        print("\n")
		
		
		#Write Code here





# Driver program to the above graph class
if __name__ == "__main__":
	V = 5
	graph = Graph(V)
	graph.add_edge(0, 1)
	graph.add_edge(0, 4)
	graph.add_edge(1, 2)
	graph.add_edge(1, 3)
	graph.add_edge(1, 4)
	graph.add_edge(2, 3)
	graph.add_edge(3, 4)

	graph.print_graph()
```
## OUTPUT

<img width="842" height="508" alt="image" src="https://github.com/user-attachments/assets/18be4238-8a38-4ee5-81bf-2c991a7586f6" />

## RESULT
Thus, the adjacency list representation of the given undirected graph is successfully constructed and printed.
