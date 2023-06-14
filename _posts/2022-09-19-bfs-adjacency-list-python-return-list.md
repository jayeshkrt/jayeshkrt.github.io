---
title: Perform DFS on Adjacency List and Return List as result in Python
category: graph
tags: BFS graph python SdeSheetChallenge
---
{% include google-analytics.html %}

# How to Perform BFS (Breadth First Search) on a given Ajacency List and return a List in Python?

You will be given an adjacency list (list of lists), and will be reuired to perform BFS on all the nodes and store the results of BFS in a list and return it. 

Here is the code to do the same

Note: The code also lists how to take input of graph in python, just in case you need it in an interview

```python
# store result of BFS in a list
# refer: https://practice.geeksforgeeks.org/problems/bfs-traversal-of-graph/1

class Solution:
	def __init__(self):
		self.result = []

	def dfs(self, adj, startNode):
		# create an empty queue to store
		# the child whose further children will be visited
		queue = []

		# this list keeps track if we have visited the node or not
		visited = []

		# add the starting node to both visited and queue
		queue.append(startNode)
		visited.append(startNode)

		# now we will keep adding the children in the queue
		# and keep visiting and adding the children until
		# all the children nodes are exhausted
		while queue:
			# remove the first element of queue
			currentNode = queue.pop(0)
			# as dfs has been performed on it just now
			# we add it to the result
			self.result.append(currentNode)

			# loop the same above step to all the children of current node
			for child in adj[currentNode]:
				if child not in visited:
					visited.append(child)
					queue.append(child)


	def bfsOfGraph(self, V, adj):
		# code here

		# call the function that does dfs with starting node (i.e. 0)
		self.dfs(adj, 0)

		# return the list stored
		return self.result

def main():

	# take input from the user

	# take vertices and no_of edges as input
	V, E = map(int, input().split())


	# create an empty adjacent list 
	adj = []

	# add empty list for each vertex
	for i in range(V+1):
		temp = []
		adj.append(temp)

	# now the consecutive lines contain the edges, so take input of that
	for i in range(E):
		first, second = map(int, input().split())
		# store the entries in the adjacency list
		adj[first].append(second)
		adj[second].append(first)

	
	# create an object of Solution class
	sol = Solution()

	# call the bfsOfGraph funtion
	print(sol.bfsOfGraph(V, adj))


if __name__ == '__main__':
	main()
```
