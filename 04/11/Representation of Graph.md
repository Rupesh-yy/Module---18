## A.REPRESENTATION OF GRAPH
## AIM
To write a Python program that generates an undirected simple graph (no self-loops and no multiple edges) from a given fixed degree sequence and displays the corresponding adjacency matrix.

## ALGORITHM
1.Start
2.Read the number of vertices and the degree sequence for each vertex.
3.Create an n × n adjacency matrix, initially filled with 0.
4.For each pair of vertices (i, j) where i < j:
  *If both degseq[i] > 0 and degseq[j] > 0, then:
    *Set mat[i][j] = 1 and mat[j][i] = 1
    *Decrease both degrees by 1
5.Continue until all vertex pairs are processed.
6.Print the adjacency matrix in the required format.
7.End

## PROGRAM
```
# Python3 program to generate a graph
# for a given fixed degrees

# A function to print the adjacency matrix.
def printMat(degseq, n):
	
	# n is number of vertices
		
	# written code
	mat = [[0] * n for i in range(n)]

	for i in range(n):
		for j in range(i + 1, n):

			# For each pair of vertex decrement
			# the degree of both vertex.
			if (degseq[i] > 0 and degseq[j] > 0):
				degseq[i] -= 1
				degseq[j] -= 1
				mat[i][j] = 1
				mat[j][i] = 1
	
	
	# Print the result in specified form
	print("      ", end ="")
	for i in range(n):
		print(" ", "(", i, ")", end ="")
	print()
	print()
	for i in range(n):
		print("  ", "(", i, ")", end = " ")
		for j in range(n):
			print("  ", mat[i][j], end = " ")
		print()

# Driver Code
degseq=[]
for i in range(0, 5):
    ele = int(input())
  
    degseq.append(ele)
#degseq =[v0,v1,v2,v3,v4]

n = len(degseq)
printMat(degseq, n)

```
## OUTPUT
<img width="1124" height="350" alt="image" src="https://github.com/user-attachments/assets/a16b72f3-80d6-47a3-a26c-2ec3aa53154f" />

## RESULT
Thus, an undirected graph satisfying the given degree sequence is successfully generated.
