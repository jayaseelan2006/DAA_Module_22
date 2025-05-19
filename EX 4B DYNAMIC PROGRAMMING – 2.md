# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm
1. Take two strings as input.
2. Create a table to store lengths of matching characters in a row-wise manner.
3. If characters match, increase the value from the diagonal cell by 1; else, put 0.
4. Keep track of the maximum value in the table (this is the length of the longest common substring).
5. Use the max value's position to extract the substring from the original string.  
## Program:
```
/*
Program to implement the longest common substring problem

.
Developed by: JAYASEELAN U
Register Number:  212223220039
*/
```
```
def lcw(u, v):
    n, m = len(u), len(v)
    dp = [[0] * (m + 1) for _ in range(n + 1)]
    max_len = 0
    end_index = 0

    for i in range(1, n + 1):
        for j in range(1, m + 1):
            if u[i - 1] == v[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] + 1
                if dp[i][j] > max_len:
                    max_len = dp[i][j]
                    end_index = i
            else:
                dp[i][j] = 0

    return u[end_index - max_len:end_index]

u = input()
v = input()
result = lcw(u, v)
print("The longest common substring is", result)
```
## Output:
![Screenshot 2025-05-07 104144](https://github.com/user-attachments/assets/d6834541-fe0f-4ac0-829d-3e1ea830cd2c)
## Result:
Thus the program was executed successfully for finding the longest common substring .
