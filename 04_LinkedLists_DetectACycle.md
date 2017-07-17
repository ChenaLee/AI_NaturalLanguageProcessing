# [Data Structures] Linked Lists: Detect A Cycle

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-linked-list-cycle.

The following is the description of the challenge.

>A linked list is said to contain a cycle if any node is visited more than once while traversing the list.
Complete the function provided in the editor below. It has one parameter: a pointer to a Node object named **head** that points to the head of a linked list. Your function must return a boolean denoting whether or not there is a cycle in the list. If there is a cycle, return **true**; otherwise, return **false**.

My submission with comments was the following.


```
"""
Detect a cycle in a linked list. Note that the head pointer may be 'None' if the list is empty.

A Node is defined as: 
 
    class Node(object):
        def __init__(self, data = None, next_node = None):
            self.data = data
            self.next = next_node
"""
def help(nd):
    if nd.data == "visited":                #Return true for visited node
        return True
    else:
        nd.data = "visited"                 #If the node has not been visited before, set data as "visited"
        if nd.next != None:                 #If next node exists 
            newnd = nd.next
            return help(newnd)              # Repeat the same with the next node
        else:
            return False                    #If next node doesn't exist, stop and return false, since this means there is no cycle

def has_cycle(head):
    if head == None:                        #If the first node is None
        return False                        # There is no cycle
    else:
        head.data = None                    #Set head's data as None (initialization)
        return help(head)                   # call helper function that does all the work.
        
```
