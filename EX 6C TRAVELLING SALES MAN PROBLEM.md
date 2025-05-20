# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE:
## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)

## Algorithm:
```
1. Define a graph with distances between V cities and select a starting city s.
2. Generate all permutations of the other cities excluding s.
3. For each permutation, calculate total route cost from s through the permutation and back to s.
4. Track and update the minimum route cost found.
5. Return the minimum cost as the shortest route covering all cities once.
6. Note: This brute-force method is feasible only for small V due to factorial complexity.
```

## Program:
```
Developed by: YOGESH V S
Register Number: 212222040185

from sys import maxsize
from itertools import permutations
V = 4
 
def travellingSalesmanProblem(graph, s):
    ##Write your code
    vertex = [] 
    for i in range(V): 
        if i != s: 
            vertex.append(i) 
    min_path = maxsize 
    next_permutation=permutations(vertex)
    for i in next_permutation:

        current_pathweight = 0
        k = s 
        for j in i: 
            current_pathweight += graph[k][j] 
            k = j 
        current_pathweight += graph[k][s] 
        min_path = min(min_path, current_pathweight) 
         
    return min_path

if __name__ == "__main__":
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```

## Output:
![Screenshot 2025-05-06 115133](https://github.com/user-attachments/assets/85b4d8a7-d453-4a9c-a176-40714b7d37f8)

## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
