# print-ascii-binary-tree
Simple code that prints a binary tree in ASCII form.

## What does it do?
Given a binary tree represented as an array, it prints the tree in a friendly ASCII output. For example, given the array `{ 16, 4, 10, 14, 7, 9, 3, 2, 8, 1 }` the output will be:
```
      16
     /   \
   4      10
  / \     / \
14   7   9   3
 ^   ^
2 8 1
```

The 
## Known limitations
The code takes the number of digits of the node values into account and adjust the padding required to obtain the ASCII output accordingly. However, if the value of an edge node is larger than 2 digits then the rest of the edge nodes will be incorrectly padded. For the other non-edge nodes, similarly if their values are too long there will also be padding errors.

## How does it work?
There are 2 problems that need to be solved: how many whitespace characters to leave between 1) the node values and 2) the edges of the binary tree. Starting from a simple example that only considers 1-digit node values we can quickly spot some rules. Let's have a look below:

![image](https://github.com/luckerby/print-ascii-binary-tree/assets/31319583/4da9599a-67ba-42f5-a644-722fde71bb8d)

There are a few distinct categories of whitespaces (padding) whose number we need to compute as we go along each row:
- Before the very first node value (yellow)
- Between the successive node values (blue). Note that these are identical
- Before the first edge (orange)
- Between the edges connecting a node to its children (green)
- Between the edges of different nodes (plum)
