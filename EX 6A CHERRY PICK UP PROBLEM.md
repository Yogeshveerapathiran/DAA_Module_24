# EX 6A CHERRY PICK UP PROBLEM
## DATE:
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.

## Algorithm:
```
1. Initialize 3D DP `dp[row][col1][col2]` for max cherries collected by two robots.
2. Set base case: robots start at top row, columns 0 and last.
3. Iterate row-wise, updating DP for all robot position pairs.
4. Calculate cherries picked, avoiding double counting.
5. Update DP using previous row’s valid moves `(col1 ± 1, col2 ± 1)`.
6. Return max cherries when robots reach the last row.
```

## Program:
```
Developed by: YOGESH V S
Register Number:212222040185

class Solution(object):
    def cherryPickup(self, grid):
        ROW_NUM = len(grid)
        COL_NUM = len(grid[0])
        dp = [[[float('-inf')] * COL_NUM for _ in range(COL_NUM)] for _ in range(ROW_NUM)]
        dp[0][0][COL_NUM - 1] = grid[0][0] + grid[0][COL_NUM - 1]
        for i in range(1, ROW_NUM):
            for j1 in range(COL_NUM):
                for j2 in range(COL_NUM):
                    curr_cherries = grid[i][j1]
                    if j1 != j2:
                        curr_cherries += grid[i][j2]
                    for prev_j1 in range(j1 - 1, j1 + 2):
                        for prev_j2 in range(j2 - 1, j2 + 2):
                            if 0 <= prev_j1 < COL_NUM and 0 <= prev_j2 < COL_NUM:
                                prev_cherries = dp[i - 1][prev_j1][prev_j2]
                                dp[i][j1][j2] = max(dp[i][j1][j2], curr_cherries + prev_cherries)
        
        return max(0, dp[ROW_NUM - 1][0][COL_NUM - 1])
        
grid=[[3,1,1],
      [2,5,1],
      [1,5,5],
      [2,1,1]]
ob=Solution()
print(ob.cherryPickup(grid))
```

## Output:
![Screenshot 2025-05-06 114433](https://github.com/user-attachments/assets/02d18f39-8107-461a-aea7-6361adda4773)

## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
