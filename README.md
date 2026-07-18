# Binary-Tree-Preorder-Traversal
class TreeNode:
    def __init__(self,val):
        self.val=val
        self.left=None
        self.right=None
def insert(root,val):
    if root is None:
        return TreeNode(val)
    if val<root.val:
        root.left=insert(root.left,val)
    else:
        root.right=insert(root.right,val)
    return root
def preorderTraversal(root):
    result=[]
    def preorder(node):
        if node is None:
            return
        result.append(node.val)
        preorder(node.left)
        preorder(node.right)
    preorder(root)
    return result
n=int(input("Enter number of nodes:"))
root=None
print("Enter node values:")
for _ in range(n):
    value=int(input())
    root=insert(root,value)
print("Preorder Traversal:")
print(*preorderTraversal(root))
