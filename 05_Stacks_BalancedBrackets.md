# [Data Structures] Stacks: Balanced Brackets

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-balanced-brackets.

The following is the description of the challenge.

>A bracket is considered to be any one of the following characters: (, ), {, }, [, or ]. Two brackets are considered to be a matched pair if the an opening bracket (i.e., (, [, or {) occurs to the left of a closing bracket (i.e., ), ], or }) of the exact same type. There are three types of matched pairs of brackets: [], {}, and (). Given **n** strings of brackets, determine whether each sequence of brackets is balanced. If a string is balanced, print **YES** on a new line; otherwise, print **NO** on a new line. 

My submission with comments was the following.


```
def is_matched(expression):
    stack = []                                                      #Empty Stack
    dict = {"{":"}", "[":"]", "(":")"}                              #Dictionary
    
    for ch in expression:                                           #For every character(bracket) in the given string of brackets
        if ch in dict:                                              #   if the character is in dictionary(opening brackets)
            stack.append(ch)                                        #       add to the stack
        else:                                                       #   Otherwise(closing brackets),
            if len(stack)==0 or ch != dict.get(stack[len(stack)-1]):#       if stack is empty Or the bracket is not matching with the most recent opening bracket
                return False                                        #           Return False
            else:                                                   #       if matching
                stack.pop()                                         #           pop the most recent opening bracket from the stack
                
    if len(stack)!=0:                                               #after going through everything, if stack is not empty
        return False                                                #   not balanced, return false
    else:                                                           #if stack is empty
        return True                                                 #   balanced. return true

t = int(input().strip())
for a0 in range(t):
    expression = input().strip()
    if is_matched(expression) == True:
        print("YES")
    else:
        print("NO")
        
```
