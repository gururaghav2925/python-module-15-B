# Python Program: Build a Binary Search Tree Using a Built-in Function

## Aim
To create a binary search tree (BST) in Python using a recursive function. The program gets input from the user, builds the BST from a sorted list, prints the post-order traversal, and verifies if the constructed tree is a valid BST.

## Procedure
1. Define a `Node` class with attributes for value, left child, and right child.
2. Accept the number of elements and their values from the user.
3. Sort the input list.
4. Define a recursive function `def _build_bst_from_sorted_values(sorted_values):` to:
   - Find the middle value and make it the root.
   - Recursively build the left and right subtrees.
   - Return the constructed BST.
5. Define a function to print the post-order traversal of the BST.
6. Define a function to check if the tree is a valid BST.
7. Print the post-order traversal and the result of BST validation.

## Python Program
```python
from binarytree import Node
def _build_bst_from_sorted_values(sorted_values):
    
    if len(sorted_values) == 0:
        return None
    mid_index = len(sorted_values) // 2
    root = Node(sorted_values[mid_index])
    root.left = _build_bst_from_sorted_values(sorted_values[:mid_index])
    root.right = _build_bst_from_sorted_values(sorted_values[mid_index + 1 :])  
    return (root)

a=[]
size=int(input())
for i in range(0,size):
  val=int(input())
  a.append(val)
x=sorted(a)
l=_build_bst_from_sorted_values(x)
print(l.postorder)
print(l.is_bst)
```
## Output:
![image](https://github.com/user-attachments/assets/459e6d01-d310-47a8-9f86-f7909db939c7)

## Result:
Thus program Accepts float values from the user,Builds a balanced binary search tree from the sorted input list using recursion,Displays the post-order traversal of the tree,Verifies and prints whether the tree satisfies BST properties.
