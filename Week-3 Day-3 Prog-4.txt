
def floorInBST(root, X):

    # Base Case
    if root is None:
        return -1

    # Find the floor in left sub tree
    leftFloor = floorInBST(root . left, X)

    # Find the floor in right sub tree
    rightFloor = floorInBST(root . right, X)

    # Let the answer be -1
    ans = -1

    # If right floor is less than 'X' and but greater then left floor
    if (leftFloor <= rightFloor and rightFloor <= X):
        ans = rightFloor

    # If left floor is less than 'X' and but greater then right floor
    if (leftFloor > rightFloor and leftFloor <= X):
        ans = leftFloor


    # If root . data is less than 'X' and greater than 'ans' then root value is more close to 'X'
    if (root.data > ans and root.data <= X):
        ans = root.data
        
    return ans


