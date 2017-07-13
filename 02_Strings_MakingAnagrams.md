# [Data Structures] Strings: Making Anagrams

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-making-anagrams.

The following is the description of the challenge.

>Given two strings, **a** and **b**, that may or may not be of the same length, determine the minimum number of character deletions required to make **a** and **b** anagrams. Any characters can be deleted from either of the strings.

My submission with comments was the following.

```
def number_needed(a, b):                  # a and b are the two strings
    count=0                               # count for the location of the character in a that we are looking at
    for ch in a:                          # rotate every charater in a (one of the string)
        posB = b.find(ch)                 # find position of the same character in b (the first one appear)
        if posB >=0:                      # if exists,
            a = a[:count] +a[count+1:]    # delete that character (one each) from both of the strings
            b = b[:posB] + b[posB+1:]
        else:
            count+=1                      # otherwise, just increase count to look log the location
    return len(a)+len(b)                  # after going through every character in a, return the
                                          #   number of remaining characters in a and b, which is
                                          #   the number of deletions needed

a = input().strip()
b = input().strip()

print(number_needed(a, b))
```
