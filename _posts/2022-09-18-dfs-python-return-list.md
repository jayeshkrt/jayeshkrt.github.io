---
title: Return result as a List after Performing DFS (Depth First Search) in Python
date: 2022-09-17 12:06:00
category: graph
tags: graph DFS input/output SdeSheetChallenge 
---
{% include google-analytics.html %}

# How to store the result of DFS (Depth First Search) in a List in Python

In coding probs on websites, you are given an adjacency list and number of vertices as input. You are required to perform DFS (Depth First Search), and store the vertices visited in a list and return back

Here's the code to do the same:
```python
# given an adjacency list, perform dfs and store the output in a list and return it
# Refer : https://practice.geeksforgeeks.org/problems/depth-first-traversal-for-a-graph/1

class Solution:
	def __init__(self):
		# a variable that can be accessed by every function in the class
		self.result = []

	# helper function that performs actual DFS by visiting every node of 
	# the graph and adds the current node to the list named "result"
	def dfs(self, adj, node):
		# add the current node the result
		self.result.append(node)

		# visit every child node and perform dfs on it
		for child in adj[node]:
			# do the DFS only if it is not already visited and counted in the result
			if child not in self.result:
				self.dfs(adj,child)

	# THIS FUNCTION IS GIVEN ON STARTER TEMPLATE IN THE PROBLEM
	def dfsOfGraph(self, V, adj):
		# your code goes here

		# V is number of vertices
		# adj is adjacency list

		# we start with the first node which is 0. 
		# That's why 0 is used as input node below. 
		# The DFS will be perfomed on further nodes successively
		self.dfs(adj, 0)

		# after the DFS is done, return the visited nodes stored in the result
		return self.result
```

Note that, in the above code, we took advantage of the `class Solution`. We added an `__init__(self)` method. This helped us declare a sort of global variable that can be accessed by any function in the class.
