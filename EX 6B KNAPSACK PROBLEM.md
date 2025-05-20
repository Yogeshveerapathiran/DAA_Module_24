# EX 6B KNAPSACK PROBLEM
## DATE:
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.

## Algorithm:
```
1. Initialize 2D DP table `K[n+1][W+1]`.
2. Iterate through items and capacities.
3. Set `K[i][w] = 0` if item index or capacity is 0.
4. If item weight ≤ capacity, set `K[i][w]` to max of including or excluding the item.
5. Otherwise, set `K[i][w]` to value from previous item at same capacity.
6. Return `K[n][W]` as the maximum value achievable.
```

## Program:
```
Developed by: YOGESH V S
Register Number:212222040185

def knapSack(W, wt, val, n):
    ########## Add your code here #########
    K = [[0 for x in range(W + 1)] for x in range(n + 1)]
    for i in range(n + 1):
        for w in range(W + 1):
            if i == 0 or w == 0:
                K[i][w] = 0
            elif wt[i-1] <= w:
                K[i][w] = max(val[i-1]+ K[i-1][w-wt[i-1]],K[i-1][w])
            else:
                K[i][w] = K[i-1][w]
 
    return K[n][W]

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```

## Output:
![Screenshot 2025-05-06 114853](https://github.com/user-attachments/assets/47637dfb-95fd-4273-adb1-d876101cd06f)

## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
