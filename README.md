# assignment-3

1st problem:-

class BinaryTree:

    def __init__(self, value):

        self.left = None
        self.right = None
        self.value = value

    def insert(self, value):

        if self.value:
            if data < self.value:
                if self.left is None:
                    self.left = BinaryTree(value)
                else:
                    self.left.insert(value)
            elif data > self.value:
                if self.right is None:
                    self.right = BinaryTree(value)
                else:
                    self.right.insert(value)
        else:
            self.value = value

    def PrintTree(self):
        if self.left:
            self.left.PrintTree()
        print( self.data),
        if self.right:
            self.right.PrintTree()

root = BinaryTree(100)
root.insert(50)
root.insert(55)
root.insert(60)
root.insert(20)
root.insert(52)


root.PrintTree()

2nd problem:-

# define a Class Tree, to intiate the binary tree
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left = None
        self.right = None
 
def height(root):
 
    # Check if the binary tree is empty
    if root is None:
        # If TRUE return 0
        return 0 
    # Recursively call height of each node
    leftAns = height(root.left)
    rightAns = height(root.right)
 
    # Return max(leftHeight, rightHeight) at each iteration
    return max(leftAns, rightAns) + 1
 
# Test the algorithm
root = TreeNode(1)
root.left = TreeNode(2)
root.right = TreeNode(3)
root.left.left = TreeNode(4)
 
print("Height of the binary tree is: " + str(height(root)))

3rd problem:-

pre-order
class Node:
	def __init__(self, v):
		self.data = v
		self.left = None
		self.right = None

# Preorder Traversal
def printPreOrder(node):
	if node is None:
		return
	# Visit Node
	print(node.data, end = " ")

	# Traverse left subtree
	printPreOrder(node.left)

	# Traverse right subtree
	printPreOrder(node.right)

# Driver code
if __name__ == "__main__":
	# Build the tree
	root = Node(100)
	root.left = Node(20)
	root.right = Node(200)
	root.left.left = Node(10)
	root.left.right = Node(30)
	root.right.left = Node(150)
	root.right.right = Node(300)

	# Function call
	print("Preorder Traversal: ", end = "")
	printPreOrder(root)

 post order:
 
 class Node:
	def __init__(self, v):
		self.data = v
		self.left = None
		self.right = None

# Preorder Traversal
def printPostOrder(node):
	if node is None:
		return

	# Traverse left subtree
	printPostOrder(node.left)

	# Traverse right subtree
	printPostOrder(node.right)
	
	# Visit Node
	print(node.data, end = " ")

# Driver code
if __name__ == "__main__":
	# Build the tree
	root = Node(100)
	root.left = Node(20)
	root.right = Node(200)
	root.left.left = Node(10)
	root.left.right = Node(30)
	root.right.left = Node(150)
	root.right.right = Node(300)

	# Function call
	print("Postorder Traversal: ", end = "")
	printPostOrder(root)

in-order:

# Python3 code to implement the approach

# Class describing a node of tree
class Node:
	def __init__(self, v):
		self.left = None
		self.right = None
		self.data = v

# Inorder Traversal
def printInorder(root):
	if root:
		# Traverse left subtree
		printInorder(root.left)
		
		# Visit node
		print(root.data,end=" ")
		
		# Traverse right subtree
		printInorder(root.right)

# Driver code
if __name__ == "__main__":
	# Build the tree
	root = Node(100)
	root.left = Node(20)
	root.right = Node(200)
	root.left.left = Node(10)
	root.left.right = Node(30)
	root.right.left = Node(150)
	root.right.right = Node(300)

	# Function call
	print("Inorder Traversal:",end=" ")
	printInorder(root)

4th problem:-

# Python3 program to print
# leaf nodes from left to right

# Binary tree node
class Node:

	def __init__(self, data):
		self.data = data
		self.left = None
		self.right = None

# Function to print leaf
# nodes from left to right
def printLeafNodes(root: Node) -> None:

	# If node is null, return
	if (not root):
		return

	# If node is leaf node,
	# print its data
	if (not root.left and
		not root.right):
		print(root.data,
			end = " ")
		return

	# If left child exists,
	# check for leaf recursively
	if root.left:
		printLeafNodes(root.left)

	# If right child exists,
	# check for leaf recursively
	if root.right:
		printLeafNodes(root.right)

# Driver Code
if __name__ == "__main__":

	# Let us create binary tree shown in
	# above diagram
	root = Node(1)
	root.left = Node(2)
	root.right = Node(3)
	root.left.left = Node(4)
	root.right.left = Node(5)
	root.right.right = Node(8)
	root.right.left.left = Node(6)
	root.right.left.right = Node(7)
	root.right.right.left = Node(9)
	root.right.right.right = Node(10)

	# print leaf nodes of the given tree
	printLeafNodes(root)

5th problem:-

##bfs
# Python3 Program to print BFS traversal
# from a given source vertex. BFS(int s)
# traverses vertices reachable from s.

from collections import defaultdict


# This class represents a directed graph
# using adjacency list representation
class Graph:

	# Constructor
	def __init__(self):

		# Default dictionary to store graph
		self.graph = defaultdict(list)

	# Function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# Function to print a BFS of graph
	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True

		while queue:

			# Dequeue a vertex from
			# queue and print it
			s = queue.pop(0)
			print(s, end=" ")

			# Get all adjacent vertices of the
			# dequeued vertex s.
			# If an adjacent has not been visited,
			# then mark it visited and enqueue it
			for i in self.graph[s]:
				if visited[i] == False:
					queue.append(i)
					visited[i] = True


# Driver code
if __name__ == '__main__':

	# Create a graph given in
	# the above diagram
	g = Graph()
	g.addEdge(0, 1)
	g.addEdge(0, 2)
	g.addEdge(1, 2)
	g.addEdge(2, 0)
	g.addEdge(2, 3)
	g.addEdge(3, 3)

	print("Following is Breadth First Traversal"
		" (starting from vertex 2)")
	g.BFS(2)

 
##dfs
# Using a Python dictionary to act as an adjacency list
graph = {
  '5' : ['3','7'],
  '3' : ['2', '4'],
  '7' : ['8'],
  '2' : [],
  '4' : ['8'],
  '8' : []
}

visited = set() # Set to keep track of visited nodes of graph.

def dfs(visited, graph, node):  #function for dfs 
    if node not in visited:
        print (node)
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited, graph, neighbour)

# Driver Code
print("Following is the Depth-First Search")
dfs(visited, graph, '5')

6th problem:-

# Python program to find sum of all left leaves

# A Binary tree node
class Node:
	# Constructor to create a new Node
	def __init__(self, key):
		self.key = key
		self.left = None
		self.right = None

# A utility function to check if a given node is leaf or not
def isLeaf(node):
	if node is None:
		return False
	if node.left is None and node.right is None:
		return True
	return False

# This function return sum of all left leaves in a
# given binary tree
def leftLeavesSum(root):

	# Initialize result
	res = 0
	
	# Update result if root is not None
	if root is not None:

		# If left of root is None, then add key of
		# left child
		if isLeaf(root.left):
			res += root.left.key
		else:
			# Else recur for left child of root
			res += leftLeavesSum(root.left)

		# Recur for right child of root and update res
		res += leftLeavesSum(root.right)
	return res

# Driver program to test above function

# Let us construct the Binary Tree shown in the above function
root = Node(20)
root.left = Node(9)
root.right = Node(49)
root.right.left = Node(23)	
root.right.right = Node(52)
root.right.right.left = Node(50)
root.left.left = Node(5)
root.left.right = Node(12)
root.left.right.right = Node(12)
print ("Sum of left leaves is", leftLeavesSum(root))

7th problem:-

# Python3 program to implement the
# above approach

# function to find Sum of all of the
# nodes of given perfect binary tree
def SumNodes(l):
	
	# no of leaf nodes
	leafNodeCount = pow(2, l - 1)

	# list of vector to store nodes of
	# all of the levels
	vec = [[] for i in range(l)]

	# store the nodes of last level
	# i.e., the leaf nodes
	for i in range(1, leafNodeCount + 1):
		vec[l - 1].append(i)

	# store nodes of rest of the level
	# by moving in bottom-up manner
	for i in range(l - 2, -1, -1):
		k = 0

		# loop to calculate values of parent nodes
		# from the children nodes of lower level
		while (k < len(vec[i + 1]) - 1):

			# store the value of parent node as
			# Sum of children nodes
			vec[i].append(vec[i + 1][k] +
						vec[i + 1][k + 1])
			k += 2

	Sum = 0

	# traverse the list of vector
	# and calculate the Sum
	for i in range(l):
		for j in range(len(vec[i])):
			Sum += vec[i][j]

	return Sum

# Driver Code
if __name__ == '__main__':
	l = 3

	print(SumNodes(l))

8th problem:-

# Python3 implementation to count subtrees
# that Sum up to a given value x

# class to get a new node


class getNode:
	def __init__(self, data):

		# put in the data
		self.data = data
		self.left = self.right = None

# function to count subtrees that
# Sum up to a given value x


def countSubtreesWithSumX(root, count, x):

	# if tree is empty
	if (not root):
		return 0

	# Sum of nodes in the left subtree
	ls = countSubtreesWithSumX(root.left,
							count, x)

	# Sum of nodes in the right subtree
	rs = countSubtreesWithSumX(root.right,
							count, x)

	# Sum of nodes in the subtree
	# rooted with 'root.data'
	Sum = ls + rs + root.data

	# if true
	if (Sum == x):
		count[0] += 1

	# return subtree's nodes Sum
	return Sum

# utility function to count subtrees
# that Sum up to a given value x


def countSubtreesWithSumXUtil(root, x):

	# if tree is empty
	if (not root):
		return 0

	count = [0]

	# Sum of nodes in the left subtree
	ls = countSubtreesWithSumX(root.left,
							count, x)

	# Sum of nodes in the right subtree
	rs = countSubtreesWithSumX(root.right,
							count, x)

	# if tree's nodes Sum == x
	if ((ls + rs + root.data) == x):
		count[0] += 1

	# required count of subtrees
	return count[0]


# Driver Code
if __name__ == '__main__':

	# binary tree creation
	#		 5
	#		 / \
	#	 -10	 3
	#	 / \ / \
	#	 9 8 -4 7
	root = getNode(5)
	root.left = getNode(-10)
	root.right = getNode(3)
	root.left.left = getNode(9)
	root.left.right = getNode(8)
	root.right.left = getNode(-4)
	root.right.right = getNode(7)

	x = 7

	print("Count =",
		countSubtreesWithSumXUtil(root, x))

9th problem:-

# A queue based Python3 program to find
# maximum sum of a level in Binary Tree
from collections import deque

# A binary tree node has data, pointer
# to left child and a pointer to right
# child
class Node:
	
	def __init__(self, key):
		
		self.data = key
		self.left = None
		self.right = None

# Function to find the maximum sum
# of a level in tree
# using level order traversal
def maxLevelSum(root):
	
	# Base case
	if (root == None):
		return 0

	# Initialize result
	result = root.data
	
	# Do Level order traversal keeping
	# track of number
	# of nodes at every level.
	q = deque()
	q.append(root)
	
	while (len(q) > 0):
		
		# Get the size of queue when the
		# level order traversal for one
		# level finishes
		count = len(q)

		# Iterate for all the nodes in
		# the queue currently
		sum = 0
		while (count > 0):
			
			# Dequeue an node from queue
			temp = q.popleft()

			# Add this node's value to current sum.
			sum = sum + temp.data

			# Enqueue left and right children of
			# dequeued node
			if (temp.left != None):
				q.append(temp.left)
			if (temp.right != None):
				q.append(temp.right)
				
			count -= 1

		# Update the maximum node count value
		result = max(sum, result)

	return result
	
# Driver code
if __name__ == '__main__':
	
	root = Node(1)
	root.left = Node(2)
	root.right = Node(3)
	root.left.left = Node(4)
	root.left.right = Node(5)
	root.right.right = Node(8)
	root.right.right.left = Node(6)
	root.right.right.right = Node(7)

	# Constructed Binary tree is:
	#			 1
	#		 / \
	#		 2	 3
	#	 / \	 \
	#	 4 5	 8
	#				 / \
	#			 6	 7
	print("Maximum level sum is", maxLevelSum(root))

10th problem:-

# Recursive Python3 program to print
# odd level nodes

# Utility method to create a node
class newNode:
	def __init__(self, data):
		self.data = data
		self.left = self.right = None

def printOddNodes(root, isOdd = True):
	
	# If empty tree
	if (root == None):
		return

	# If current node is of odd level
	if (isOdd):
		print(root.data, end = " ")

	# Recur for children with isOdd
	# switched.
	printOddNodes(root.left, not isOdd)
	printOddNodes(root.right, not isOdd)

# Driver code
if __name__ == '__main__':
	root = newNode(1)
	root.left = newNode(2)
	root.right = newNode(3)
	root.left.left = newNode(4)
	root.left.right = newNode(5)
	printOddNodes(root)









