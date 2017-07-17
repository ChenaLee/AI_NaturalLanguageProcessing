# [Data Structures] Hash Tables: Random Note

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-ransom-note.

The following is the description of the challenge.

>Given the words in the magazine and the words in the ransom note, print **Yes** if he can replicate his ransom note exactly using whole words from the magazine; otherwise, print **No**.

My submission with comments was the following.

```
def ransom_note(magazine, ransom):                                                                #Because of the large pool, simply searching through takes too long time. Need some kind of hash tables
    magazineH = [[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[]]   #Created an array of 26 arrays for each alphabet a-z
    for item in magazine:                         
        magazineH[ord(item[:1])-97].append(item)                                                  #Depending on the first alphabet of the word in magazine, put into the appropriate array
    
    for i in ransom:
        try:
            magazineH[ord(i[:1])-97].remove(i)                                                    #Try removing the word we need from the arrays
        except:
            return False                                                                          #If it fails, it means that word isn't in the magazine. return false.
    return True                                                                                   #If every removal suceeds, return true
            
m, n = map(int, input().strip().split(' '))
magazine = input().strip().split(' ')
ransom = input().strip().split(' ')
if m < n:                                                                                         #If the number of words we need is greater than the number of words in the magazine,
    answer = False                                                                                #return false
else:
    answer = ransom_note(magazine, ransom)

if(answer):
    print("Yes")
else:
    print("No")
```
