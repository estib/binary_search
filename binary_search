__author__ = 'stephenlechner'

# This function will use recursion to run a binary search across a list.
# Will only work on a sorted list.
# The program will demonstrate that binary searching is more efficient,
# time-wise, at searching through a large list than is simple iteration.
#
# TODO: refactor to allow searching for multiple indices with the same
#       searched value. 

import time


class Exc(Exception):
    pass


def binary_search(search_list, target):
    if len(search_list) > 2:
        mid = int(round(len(search_list) / 2)) - 1
        if target > search_list[mid]:
            return mid + binary_search(search_list[mid+1:], target) + 1
        elif target < search_list[mid]:
            return binary_search(search_list[:mid-1], target)
        else:
            return mid
    elif len(search_list) == 2:
        if target == search_list[0]:
            return 0
        elif target == search_list[1]:
            return 1
        else:
            raise Exc("Error: what you searched for isn't in the list.")
    elif target == search_list[0]:
        return 0
    else:
        raise Exc("Error: what you searched for isn't in the list.")

# build a list of integers. 
find = 11235

the_list = []
for x in range(1, find+1):
    the_list.append(x)

the_list.sort()

# binary search, and count the time it takes
time_start = time.time()

ind = binary_search(the_list, find)

print str(ind), "runtime:", str(time.time() - time_start)

# iterative search, and count the time it takes
time_start = time.time()

for x in range(0, len(the_list)):
    if the_list[x] == find:
        ind = x

print str(ind), "runtime:", str(time.time() - time_start)
