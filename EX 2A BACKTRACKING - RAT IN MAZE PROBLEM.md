# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 13/03/2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.

## Algorithm
1. Start from the top-left cell of the maze.
2. Move forward only if the current cell is within bounds and not blocked (i.e., value is 1).
3. Mark the current cell in the solution path.
4. Recursively try to move right or down to reach the destination.
5. If no move leads to the destination, backtrack and unmark the cell. 

## Program:

### Program to implement Rat in a Maze.
**Developed by:** DHANALAKSHMI S  
**Register Number:** 212222040033
```
N = 4
def printSolution( sol ):
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
def isSafe( maze, x, y ):
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
    return False
def solveMaze( maze ):
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
def solveMazeUtil(maze, x, y, sol):
 
    if x==N-1 and y==N-1 and maze[x][y]==1:
        sol[x][y]=1
        return True
    if isSafe( maze, x, y ):
        sol[x][y]=1
        if solveMazeUtil(maze, x+1, y, sol):
            return True
        if solveMazeUtil(maze, x, y+1, sol):
            return True
        sol[x][y]=0
    return False
# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```
## Output:
![Screenshot 2025-05-24 204903](https://github.com/user-attachments/assets/82410475-8162-4b7a-8f7b-656eb4863dd0)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
