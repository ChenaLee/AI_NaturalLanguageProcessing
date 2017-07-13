# [Data Structures] Arrays: Left Rotation

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-array-left-rotation.

The following is the description of the challenge.

>A left rotation operation on an array of size  shifts each of the array's elements  unit to the left. For example, if left rotations are performed on array , then the array would become .
Given an array of **n** integers and a number, **d**, perform **d** left rotations on the array. Then print the updated array as a single line of space-separated integers.

In fact, it was **k** instead of **d** in the pre-written code, so I went with **k**.

My submission with comments was the following.

```
def array_left_rotation(a, n, k):                   # a: array, n: number of elements of the array, k: number of rotations
    sublist_front = a[:k]                           # Cut out the first k numbers 
    sublist_back = a[k:]                            # Cut out the rest
    sol = sublist_back +(sublist_front)             # Combine the two in the reverse order

    return sol
    

n, k = map(int, input().strip().split(' '))
a = list(map(int, input().strip().split(' ')))
answer = array_left_rotation(a, n, k);
print(*answer, sep=' ')
```
