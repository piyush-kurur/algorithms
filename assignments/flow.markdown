# Max-flow and related problems: November 3, Monday (mid-night)

Marks: 5 + 10 + 5

1. Implement the bfs algorithm on a directed graph

2. Recall that if the Ford-Fulkerson algorithm is not done carefully
   the algorithm can be exponential. In the class we discussed the
   variant which uses the bfs algorithm to make the algorithm efficient.
   This version was shown to be efficient by Edmonds and Karp. Using
   the algorithm in problem 1, implement the Edmonds-Karp variant
   of the Ford-Fulkerson algorithm.

3. Use the algorithm in problem 2 to give an algorithm for bipartite
   matching. We discussed this reduction in the class.

## Uploading instructions

The CSE programming judge is used for evaluation. Please follow the
instructions given in assignment 0.

## Input format.

For the flow problem, the input is given as a list of edges and their
capacities. The very first line just contains a single non-negative
integer say `n` which is the number of vertices in the graph. The next
linescontains the indices of the source and target. This is followed
by a series of lines which consists of the following:

```shell
u v c
```

where `u` and `v` are integers such that `0 <= u,v <= n - 1` and `c`
is a double precision number. The above line means that the capacity
of an edge between `u` to `v` is `c`. The edge list is terminated with
an "end of file", i.e. in a Unix system this means that while typing
you need to press `Control-D`

For example, the graph that we used in the class to show that
augmentation paths should be selected carefully is given below.

```shell
4
0 3
0 1 10000
0 2 10000
1 3 10000
2 3 10000
1 2 1
2 1 1
```

There are 4 vertices numbered 0,1,2,3 of which 0 is the source and 3
is the sink (this is what the first two lines describe). The rest of
the lines give the capacity in each direction.

**Important**: If an edge is omitted, it just means the capacity in
  that direction is 0. In the above graph for example, the capacity in
  the direction 1-0 is 0 where as 0-1 is 10000. For the edge 1,2 and also
  2,1 the capacities are 1.

## Output format

The output of the flow program should be as follows. The first line
should be the total s-t flow, followed by the flow along each edge.
If there is a positive flow between u and v you need to give only
that. For example for the above graph as input the algorithm should
output the following.

```shell
20000
0 1 10000
1 3 10000
0 2 10000
2 3 10000
```

## Important Note.

The nodes are numbered starting from 0 to n - 1. Please make sure that
your program adhere to the above format as we might run your code
through automated testing program.

## Some helpful suggestion

Separate out the reading and writing of graphs and flows from the main
functions. For example, for the bfs problem you need to write

(1) A function readGraph() which reads a directed graph and

(2) A separate function that does the actual bfs computation.

This way you can reuse the bfs function in the max-flow
function. Similarly, for the max-flow problem separate the reading and
writing from the main routine so that you can use it in the next
problem to compute the maximal matching.
