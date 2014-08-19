# Minimum spanning tree: Deadline to be decided.

10 marks each

1. Implement union-find data structure in your favourite language. Use
   this data structure give an implementation of Kruskal's algorithm.

2. Implement using an array a binary min-heap which also supports
   decrement-key. Use this to implement Prim's algorithm for MST.

## Uploading instructions

The CSE programming judge is used for evaluation. Please follow the
instructions given in assignment 0.

## Input format.

Your program should take the input graph in the following format: The
very first line just contains a single non-negative integer which is
the number of nodes $n$. This is followed by a series of lines which
consists of the following:

```shell
u v w
```

where u and v are integers such that 0 <= u,v <= n - 1 and w is a
double precision number. The above line means that there is an
undirected edge between u to v of weight w.

For example the complete graph with 3 nodes each having weight 3.14
would be given to the algorithm in the following format

```shell
3
0 1 3.14
1 2 3.14
2 0 3.14
```

## Output format

The output of the program should be the weight of the MST followed by
the edges. In the above case for example it would be.

```shell
6.28
0 1 3.14
0 2 3.14
```

## Important Note.

The nodes are numbered starting from 0 to n - 1. Please make sure that
your program adhere to the above format as we might run your code
through automated testing program.
