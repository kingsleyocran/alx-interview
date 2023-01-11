# 0. Minimum Operations

In a text file, there is a single character H. Your text editor can execute only two operations in this file: Copy All and Paste. Given a number n, write a method that calculates the fewest number of operations needed to result in exactly n H characters in the file.

- Prototype: def minOperations(n)
- Returns an integer
- If n is impossible to achieve, return 0


#### Example:

n = 9

H => Copy All => Paste => HH => Paste =>HHH => Copy All => Paste => HHHHHH => Paste => HHHHHHHHH

Number of operations: 6

```
carrie@ubuntu:~/0x02-minoperations$ cat 0-main.py
#!/usr/bin/python3
"""
Main file for testing
"""

minOperations = __import__('0-minoperations').minOperations

n = 4
print("Min # of operations to reach {} char: {}".format(n, minOperations(n)))

n = 12
print("Min # of operations to reach {} char: {}".format(n, minOperations(n)))

carrie@ubuntu:~/0x02-minoperations$
```

```
carrie@ubuntu:~/0x02-minoperations$ ./0-main.py
Min number of operations to reach 4 characters: 4
Min number of operations to reach 12 characters: 7
carrie@ubuntu:~/0x02-minoperations$
```


```
Run the command below to execute these test cases.
python3 -m doctest -v test_0_minoperations.txt

Operations path format:
Character in file: H
operations: copy all (bit 1) or paste (bit 0),
    e.g.; copy all and paste -> 11
    e.g.; paste only -> 01

>>> minOperations = __import__('0-minoperations').minOperations
>>> minOperations(0)
0
>>> minOperations(-1)
0
>>> minOperations(1.4)
0
>>> minOperations('1')
0

# H
>>> minOperations(1)
0

# H-(11)->HH
>>> minOperations(2)
2

# H-(11)->HH-(11)->HHHH
# H-(11)->HH-(01)->HHH-(01)->HHHH
>>> minOperations(4)
4

# H-(11)->HH-(01)->HHH-(01)->HHHH-(01)->HHHHH
>>> minOperations(5)
5

# H-(11)->HH-(01)->HHH-(01)->HHHH-(01)->HHHHH-(01)->HHHHHH-(01)->HHHHHHH
>>> minOperations(7)
7

# H-(11)->HH-(01)->HHH-(01)->HHHH-(01)->HHHHH-(01)->HHHHHH-(01)->HHHHHHH-(01)->HHHHHHHH-(01)->HHHHHHHHH-(01)->HHHHHHHHHH-(01)->HHHHHHHHHHH
>>> minOperations(11)
11

# H-(11)->HH-(01)->HHH-(11)->HHHHHH-(01)->HHHHHHHHH
>>> minOperations(9)
6

# H-(11)->HH-(01)->HHH-(11)->HHHHHH-(11)->HHHHHHHHHHHH
>>> minOperations(12)
7

# H-(11)->HH-(01)->HHH-(11)->HHHHHH-(01)->HHHHHHHHH
>>> minOperations(15)
8

```