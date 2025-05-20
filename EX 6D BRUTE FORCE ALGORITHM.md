
# EX 6D BRUTE FORCE ALGORITHM
## DATE:
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.

## Algorithm:
```
1.Take the main string and the substring as input.
2.Find the lengths of both strings.
3.Loop through the main string from index 0 to len(main) - len(substring).
4.At each position, extract a slice equal to the length of the substring.
5.Compare the slice with the substring; if they match, print the starting index.
6.Continue until all possible positions are checked.

```
## Program:
```
Developed by: YOGESH V S
Register Number:  212222040185

def match(string,sub):
    l = len(string)
    ls = len(sub)
    start = sub[0]
    for i in range(l-ls+1):
        if string[i:i+ls]==sub:
            print(f"Found at index {i}")

    ########### Add your code here #######

str1=input()
str2=input()
```

## Output:
![Screenshot 2025-05-06 115432](https://github.com/user-attachments/assets/56e4307a-680a-4d12-8b14-62b18c1c6a69)

## Result:
Thus the above program was executed successfully for searching the substring at respective index.
