# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 17/04/2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Try to assign colors (1 to m) to each vertex of the graph.
2. For each vertex, check if the chosen color is safe (no adjacent vertex has the same color).
3. If safe, assign the color and move to the next vertex recursively.
4. If coloring fails for a vertex, backtrack and try a different color.
5. If all vertices are colored successfully, print the color assignments.   

## Program:

### Program to implement Graph Coloring Problem using backtracking.
**Developed by:** DHANALAKSHMI S  
**Register Number:** 212222040033
```
class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.Graph=[[0 for column in range(vertices)]for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.V):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColourUtil(self,m,colour,v):
        if v==self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColourUtil(m,colour,v+1):
                    return True
                colour[v]=c
        return False
    def graphColouring(self,m):
        colour=[0]*self.V
        if not self.graphColourUtil(m,colour,0):
            print("No solution Exist")
            return False
        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c,end=' ')
        print()
        return True

```
## Output:
![Screenshot 2025-05-24 210114](https://github.com/user-attachments/assets/b6451a26-7eea-4ab9-8cc9-85855ae21168)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
