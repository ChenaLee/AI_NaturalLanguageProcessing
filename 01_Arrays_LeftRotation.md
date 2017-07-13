# [Data Structures] Arrays: Left Rotation

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-array-left-rotation.

The following is the description of the challenge.

>A left rotation operation on an array of size  shifts each of the array's elements  unit to the left. For example, if left rotations are performed on array , then the array would become .
Given an array of n integers and a number, d, perform  left rotations on the array. Then print the updated array as a single line of space-separated integers.



```
def array_left_rotation(a, n, k):
    sublist_front = a[0:k]
    sublist_back = a[k:]
    sol = sublist_back +(sublist_front)

    return sol
    

n, k = map(int, input().strip().split(' '))
a = list(map(int, input().strip().split(' ')))
answer = array_left_rotation(a, n, k);
print(*answer, sep=' ')
```
