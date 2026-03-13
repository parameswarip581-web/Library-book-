# Library-book-
Practice program 
class Node:
    def __init__(self, key):
        self.key = key
        self.left = None
        self.right = None
def insert(root, key):
    if root is None:
        return Node(key)
    if key < root.key:
        root.left = insert(root.left, key)
    else:
        root.right = insert(root.right, key)
    return root
def minValue(root):
    while root.left:
        root = root.left
    return root
def delete(root, key):
    if root is None:
        return root
    if key < root.key:
        root.left = delete(root.left, key)
    elif key > root.key:
        root.right = delete(root.right, key)
else:
        if root.left is None:
            return root.right
        elif root.right is None:
            return root.left
        temp = minValue(root.right)
        root.key = temp.key
        root.right = delete(root.right, temp.key)
    return root
def display(root):
    if root:
        display(root.left)
        print root.key,
        display(root.right)
root = None
root = insert(root, 101)
root = insert(root, 105)
root = insert(root, 103)
root = insert(root, 110)
print "Library Book IDs:"
display(root)
print "\nDeleting Book ID 105"
root = delete(root, 105)
print "Book IDs after deletion:"
display(root)
OUTPUT:

Library Book IDs:
101 103 105 110

Deleting Book ID 105
Book IDs after deletion:
101 103 110
