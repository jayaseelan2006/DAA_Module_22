# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:
## AIM:
To find longest common subsequence using Dynamic Programming.

## Algorithm
1. Take two strings as input.
2. Create a table to store lengths of common subsequences.
3. Fill the table using comparison of characters.
4. The last cell of the table gives the LCS length.
5. Trace back through the table to get the actual LCS.
## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming

.
Developed by: Jayaseelan U
Register Number:  212223220039
*/
```
```
def lcs(X, Y):
    m = len(X)
    n = len(Y)
    dp = [[0] * (n + 1) for _ in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] + 1
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])
    i, j = m, n
    lcs_str = []
    while i > 0 and j > 0:
        if X[i - 1] == Y[j - 1]:
            lcs_str.append(X[i - 1])
            i -= 1
            j -= 1
        elif dp[i - 1][j] > dp[i][j - 1]:
            i -= 1
        else:
            j -= 1
    return ''.join(reversed(lcs_str))

X = input()
Y = input()
result = lcs(X, Y)
print(result)
```
## Output:
![Screenshot 2025-05-07 103747](https://github.com/user-attachments/assets/ba4ab642-39b8-4d81-ac11-138bb3c51094)
## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
