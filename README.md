# Codibility
Developer Challenges

# BinaryGap solution. Exercise by Codility.

```ruby
#Author: Ikechukwu Onyenwe (my solution)
# you can write to stdout for debugging purposes, e.g.
# print("this is a debug message")

def solution(N):
    # write your code in Python 3.6

    # create containers for zeros and binary gaps found
    zeros_list = []
    binary_gap_found = []

    # create binary of any positive integer N and found its length
    binarylist = list("{0:b}".format(N))
    binarylist_length = len(binarylist)

    # iterate through the binary list
    for i in range(binarylist_length):
        bit = int(binarylist[i])
        zeros_list.append(bit)

        if bit == 1:

            # check if zeros found are bounded by 1s at the start and end (e.g. 10001) 
            # and keep as binary gap found if test is true. 
            if int(zeros_list[0]) == 1 and len(zeros_list[1:-1]) != 0 and int(zeros_list[-1]) == 1:
                binary_gap_found.append(len(zeros_list[1:-1]))
            
            # reinitialize the container
            zeros_list = []
            zeros_list.append(binarylist[i])

    # return max value of the binary gap found list or zero if no found.
    if len(binary_gap_found) > 0:
        return max(binary_gap_found)
    else: return 0
```
