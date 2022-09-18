---
title: Take Input of Graph in Python
date: 2022-09-17 11:40:00
tags: input graph competitive_programming CP python beginner
category: graph
---

# How to take an input of Graph in Python for Competitve Programming (CP) problems?

The first line generally contains number of vertices V and the next E lines denotes the Edges between the vertices.

So, the input in coding problems on websites looks like this
```
Input: 
V E
n1 n2    |
n2 n3    |
n3 n4    | E lines (edges)
n1 n5    |
n4 n2    |
```

Here's how to take the input and store in an adjacency list in Python:

```python
# take inputs V and E
V,E = map(int, input().split())

# create an empty adjacent list
adj = []

# there are V vertices so create empty lists in "adj" to store the neighbours
for i in range(V+1):
	temp = []
	adj.append(temp)

# following E lines take input and update the adjacency list
for j in range(E):
	# store the 2 integers as m and n
	m,n = map(int, input().split())
	# since it is undirected graph, both will be one another's neighbours
	adj[m].append(n)
	adj[n].append(m)

# print the list to check if the list is properly created
print(adj)
```

Example:
```
Input:
5 4
0 2
0 3
0 1 
2 4

Output:
[[2,3,1], [0], [0,4], [0], [2], []]
```