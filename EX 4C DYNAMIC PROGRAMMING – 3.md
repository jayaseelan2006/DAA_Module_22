# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.

## Algorithm
1. Take a string S as input.
2. Create a DP table L to store subsequence lengths.
3. Initialize each character in S as a palindrome of length 1.
4. Fill the table using the recurrence: if characters match, add 2; otherwise, take the max from adjacent values.
5. The length of the longest palindromic subsequence is in L[0][n-1].
## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it

.
Developed by: jayaseelan u
Register Number:  212223220039
*/
```
```
def lps(s):
    n = len(s)
    dp = [[0] * n for _ in range(n)]

    for i in range(n):
        dp[i][i] = 1

    for cl in range(2, n + 1):
        for i in range(n - cl + 1):
            j = i + cl - 1
            if s[i] == s[j] and cl == 2:
                dp[i][j] = 2
            elif s[i] == s[j]:
                dp[i][j] = dp[i + 1][j - 1] + 2
            else:
                dp[i][j] = max(dp[i + 1][j], dp[i][j - 1])

    return dp[0][n - 1]

s = input()
print("The length of the LPS is", lps(s))
```
## Output:
![Screenshot 2025-05-07 104450](https://github.com/user-attachments/assets/2da59ddd-daa9-4613-9266-6e8dd8606a9f)
## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
