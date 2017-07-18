# [Data Structures] Queues: A Tale Of Two Stacks

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-queue-using-two-stacks.

The following is the description of the challenge.

>In this challenge, you must first implement a queue using two stacks. Then process  queries, where each query is one of the following  types:
  1 x: Enqueue element  into the end of the queue.
  2: Dequeue the element at the front of the queue.
  3: Print the element at the front of the queue.

My submission with comments was the following.


```
class MyQueue(object):
    def __init__(self):
        self.data = []                  #Empty list
    
    def peek(self):
        return self.data[0]             #return the first element of the list
        
    def pop(self):
        return self.data.pop(0)         #return and delete the first element of the list
        
    def put(self, value):
        return self.data.append(value)  #add an element at the end of the list
        

queue = MyQueue()
t = int(input())
for line in range(t):
    values = map(int, input().split())
    values = list(values)
    if values[0] == 1:
        queue.put(values[1])        
    elif values[0] == 2:
        queue.pop()
    else:
        print(queue.peek())
        
```
