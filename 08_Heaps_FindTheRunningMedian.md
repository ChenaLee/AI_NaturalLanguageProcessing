# [Data Structures] Heaps: Find The Running Median

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-find-the-running-median.

The following is the description of the challenge.

>Given an input stream of **n** integers, you must perform the following task for each **i-th** integer:
Add the **i-th** integer to a running list of integers.
Find the median of the updated list (i.e., for the first element through the **i-th** element).
Print the list's updated median on a new line. The printed value must be a double-precision number scaled to decimal place (i.e., **12.3** format).

My submission with comments was the following.


```
""" Node is defined as
class node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
"""

import sys
import bisect

n = int(input().strip())                         
a = []
a_i = 0
for a_i in range(n):                                #for given n numbers
    a_t = int(input().strip())                      #given number a_t
    bisect.insort(a,a_t)                            #add a_t to the sorted array so that it is still sorted
       
    length = len(a)                                 
    if length%2 == 0:                               #if the array length is even
        print((a[length//2]+a[length//2 -1]) /2)    #find the mean of two middle numbers
    else:                                           #otherwise
        print(a[length//2]/1.0)                     #find the middle number
        
```
