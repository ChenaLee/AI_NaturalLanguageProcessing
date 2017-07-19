# [Data Structures] Tries: Contacts

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-contacts.

The following is the description of the challenge.

>We're going to make our own Contacts application! The application must perform two types of operations:
1. **add** **name**, where **name** is a string denoting a contact name. This must store **name** as a new contact in the application.
2. **find** **partial**, where **partial** is a string denoting a partial name to search the application for. It must count the number of contacts starting with **partial** and print the count on a new line.
Given **n** sequential add and find operations, perform each operation in order.

My submission was the following. I initially wanted to use tree approaches, but it did not work probably because of the memory issue with the language. However, a correct tree approach will allow you to **find** number of trees so much faster.


```
n = int(input().strip())
contacts =[[]]

for a in range(26):
    contacts.append([])
    for b in range(27):
        contacts[a].append([])

for a0 in range(n):
    op, contact = input().strip().split(' ')
    
    if op == "add":
        ind = ord(contact[:1]) - 97
        
        if len(contact) == 1:
            contacts[ind][26] = contacts[ind][26]+[contact]
        else:
            ind2 = ord(contact[1:2]) -97
            contacts[ind][ind2] = contacts[ind][ind2] + [contact]
        
    else:
        ind = ord(contact[:1]) -97
        length = len(contact)
        
        if length == 1:
            total = 0
            for n in range(27):
                total += len(contacts[ind][n])
            print(total)
        else:
            ind2 = ord(contact[1:2]) -97
            if length ==2:
                print(len(contacts[ind][ind2]))
            else:
                count = 0
                
                for b in contacts[ind][ind2]:
                    if b[:length] == contact:
                        count = count +1
        
                print(count)
        
```
