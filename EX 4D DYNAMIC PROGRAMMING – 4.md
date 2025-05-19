# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm
1. Take two strings str1 and str2.
2. If str1 is empty, return the length of str2.
3. If str2 is empty, return the length of str1.
4. If the last characters are the same, recursively solve for the remaining parts of both strings.
5. If the last characters differ, recursively compute the minimum operations for insertion, deletion, and substitution, then take the minimum.
## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

.
Developed by: jayaseelan U
Register Number:  212223220039
*/
```
```
def edit_distance(str1, str2, m, n):
    if m == 0:
        return n
    if n == 0:
        return m

    if str1[m - 1] == str2[n - 1]:
        return edit_distance(str1, str2, m - 1, n - 1)

    return 1 + min(
        edit_distance(str1, str2, m, n - 1),   
        edit_distance(str1, str2, m - 1, n),    
        edit_distance(str1, str2, m - 1, n - 1) 
    )


str1 = input()
str2 = input()
result = edit_distance(str1, str2, len(str1), len(str2))
print("Edit Distance", result)
```
## Output:
![Screenshot 2025-05-07 104728](https://github.com/user-attachments/assets/067e948e-d0df-47c9-9d39-b665302d8bdf)
## Result:
Thus the program was executed successfully for finding edit distance between two strings.
