### interviewQuestions

### What would be the time complexity of a method that uses the`binary search algorithm`to check if an integer exists in a sorted list?

O\(logN\)

### The worst-case scenarios for BST's all involve a completely unbalanced tree, which degenerates into a singly-linked list. For example, if you just add 1, 2, 3, 4, 5 in that order to a simple \(non-self-balancing\) BST implementation, then all your nodes will only have a right child. You then do not get the "halving at every step" characteristic that gives BST's their power.

In this worst-case scenario:

* **access is O\(n\)**
* **search is O\(n\)**
* **insertion is O\(n\)**
* **deletion is O\(n\)** 

**Find One Missing Number from 1 to 10**

```
def find_missing_number(list_numbers):
    n = len(list_numbers)
    total = (n+2)*(n+1)/2
    supposed_sum = sum(list_numbers)
    missing = total - supposed_sum
    return missing
```

```
def is_palindrome(input_string):
    length = len(input_string)
    middle = (length+1)/2-1
    if not input_string:
        return True
    else:
        if length%2 != 0:
            for i in range(0, length-1):
                if i < middle:
                    if input_string[i] == input_string[length-1-i]:
                        return True
                    else:
                        return False
        else:
            return False
```

### You are given an m x n 2D image matrix \(

### `List of Lists`

### \) where each integer represents a pixel. Flip it

### **in-place**

### along its horizontal axis.

##### Use nested for loops to traverse over the entire matrix. Remember this pattern for all 2D array problems :

##### `rows = len(matrix)`

##### and

##### `columns = len(matrix[0])`

##### . Once you have the row / column dimensions, write 2 for loops that traverse the entire matrix. In the inner for loop, use a temporary variable to make the swap.

```
def flip_axis(matrix):
    r = len(matrix) - 1
    c = len(matrix[0]) - 1
    i=0
    temp=0
    while i<=r:
        j=0
        while i<j<=c:
            temp = matrix[i][j]
            matrix[i][j] = matrix[i][c-j]
            matrix[i][c-j] = temp
            j=j+1
        i=i+1
```

### Q: reverse the order of column elements:

```
def flip_vertical_axis(matrix):
    r = len(matrix)-1
    c = len(matrix[0])-1
    i=0
    temp=0
    while i<=r:
        j=0
        while j<=c/2:
            temp = matrix[i][j]
            matrix[i][j] = matrix[i][c-j]
            matrix[i][c-j] = temp
            j=j+1
        i=i+1
```

### Q: reverse the order of rows elements:

\(Flip it

**in-place**

along its horizontal axis.\)

```
def flip_vertical_axis(matrix):
    r = len(matrix)-1
    c = len(matrix[0])-1
    i=0
    temp=0
    while i<=r/2:
        j=0
        while j<=c:
            temp = matrix[i][j]
            matrix[i][j] = matrix[r-i][j]
            matrix[r-i][j] = temp
            j=j+1
        i=i+1
```

### Int to binary:

```
def dec_to_bin(number):
   return dec_to_bin(number/2) + str(number%2) if number > 1 else str(number)
```

### `list.sort()`has no return value, instead it has the side effect that the instance of list that it was called on will be sorted after the method has finished

### `sorted(list)`leaves the argument unchanged and instead creates and returns a list consisting of the same elements as the argument that you passed to it

### find duplicate number in sorted list

#### set\(iterablelist\)

```
def duplicate_items(list_numbers):
    duplicate = []
    list_numbers.sort()
    length = len(list_numbers)
    for i in range(0, length-1):
        if list_numbers[i] == list_numbers[i+1]:
            duplicate.append(list_numbers[i])
    return duplicate
```

### check if characters unique in string

```
def unique_chars_in_string(input_string):
    if not input_string:
        return True
    else:
        char_set = set()
        for char in input_string:
            char_set.add(char)
        return len(char_set)==len(input_string)
```

### Bubble sort:

```
def bubble_sort(a_list):
    for i in range(len(a_list)):
        for j in range(0, len(a_list)-i-1):
            if a_list[j] > a_list[j+1]:
                temp = a_list[j+1]
                a_list[j+1] = a_list[j]
                a_list[j] = temp
    return a_list
```

#### optimized by stopping the algorithm if inner loop didn’t cause any swap:

```
def bubble_sort(a_list):
    swaped = False
    for i in range(len(a_list)):
        for j in range(0, len(a_list)-i-1):
            if a_list[j] > a_list[j+1]:
                temp = a_list[j+1]
                a_list[j+1] = a_list[j]
                a_list[j] = temp
                swaped = True
        if swaped == False:
            break
    return a_list
```

### Insert at the end of linked list without using tail:

```
def Insert(head, data):

    if (head == None):
        head = Node(data)
    else:
        current = head
        while (current.next != None):
            current = current.next
        current.next = Node(data)
    return head
```

### Reverse a singly linkedlist

#### 1. Iterative method:

**Time Complexity:**

O\(n\)

**Space Complexity:**

O\(1\)

```
class SinglyLinkedList:
    #constructor
    def __init__(self):
        self.head = None

    #method for setting the head of the Linked List
    def setHead(self,head):
        self.head = head

    def reverse(self):
        prev = None
        current = self.head
        while (current is not None):
            next = current.next
            current.next = prev
            prev = current
            current = next
        self.head = prev
```

### 2. recursive method:

```
class Node:

    # Constructor to initialize the node object
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:

    # Function to initialize head
    def __init__(self):
        self.head = None


    def reverseUtil(self, curr, prev):

        # If last node mark it head
        if curr.next is None :
            self.head = curr 

            # Update next to prev node
            curr.next = prev
            return

        # Save curr.next node for recursive call
        next = curr.next

        # And update next 
        curr.next = prev

        self.reverseUtil(next, curr) 


    # This function mainly calls reverseUtil()
    # with previous as None
    def reverse(self):
        if self.head is None:
            return
        self.reverseUtil(self.head, None)


    # Function to insert a new node at the beginning
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        self.head = new_node

    # Utility function to print the linked LinkedList
    def printList(self):
        temp = self.head
        while(temp):
            print temp.data,
            temp = temp.next


# Driver program
llist = LinkedList()
llist.push(8)
llist.push(7)
llist.push(6)
llist.push(5)
llist.push(4)
llist.push(3)
llist.push(2)
llist.push(1)

print "Given linked list"
llist.printList()

llist.reverse()

print "\nReverse linked list"
llist.printList()
```

### 

### Given a sorted list of integer ranges,  merge all overlapping ranges

#### Helper class Range:

```
class Range(object):
    def __init__(self):
        self.lower_bound = -1
        self.upper_bound = -1

    def __init__(self,lower_bound,upper_bound):
        self.lower_bound = lower_bound
        self.upper_bound = upper_bound

    def __str__(self):
        return "["+str(self.lower_bound)+","+str(self.upper_bound)+"]"
```

#### Find biggest gain:

```
def max_gain(input_list):
    gain = 0
    min = 0
    check = 0
    for i in range(0, len(input_list)-2):
        if input_list[i] < input_list[i+1]:
            if check < input_list[i+1] - input_list[i]:
                gain = input_list[i+1]
                min = input_list[i]
                check = gain - min
        else:
            min = input_list[i+1]
    return gain
```

Find the leaf nodes in binary tree:

```
# Python program to count leaf nodes in Binary Tree

# A Binary tree node
class Node:

    # Constructor to create a new node
    def __init__(self, data):
        self.data = data 
        self.left = None
        self.right = None

# Function to get the count of leaf nodes in binary tree
def getLeafCount(node):
    if node is None:
        return 0
    if(node.left is None and node.right is None):
        return 1
    else:
        return getLeafCount(node.left) + getLeafCount(node.right)
```

```
def better_fibonacci(n):
    n2 = 0
    n1 = 1
    if n == 0:
        return n2
    elif n == 1:
        return n1
    for i in range(2, n+1):
        temp = n1 + n2
        n2 = n1
        n1 = temp
    return n1
```

### Level traverse a binary tree iteratively

```
class BinaryTree:
    def __init__(self, root_node = None):
            self.root = root_node

    # Required collection modules have already been imported. 
    def number_of_full_nodes(self,root):
        queue = deque()
        queue.append(root)
        count = 0
        if root == None:
            return 0
        while len(queue) > 0:
            node = queue.popleft()
            if node.left_child:
                queue.append(node.left_child)
            if node.right_child:
                queue.append(node.right_child)
            if node.left_child and node.right_child:
                count += 1
        return count
```

### print path\(DFS recursively\)

```
def print_paths(board):
   output = []
   temp = []
   row = len(board)-1
   col = len(board[0])-1

   solution = helper(0, 0, board, output, temp, (row, col))
   return solution

def helper(i, j, board, output, temp, dim):
    if dim[0] < 0 or dim[1] < 0:
        return ['Empty']
    if dim[0] == 0 and dim[1] == 0:
        return board[0]
    if i>dim[0] or j>dim[1]:
        return

    if i == dim[0] and j == dim[1]:
        item = board[i][j]
        temp.append(item)
        path = "".join(temp)
        output.append(path)
        return output
    else:
        item = board[i][j]
        temp.append(item)
        original = temp[:]  # Current path
        helper(i,j+1,board,output,temp, dim)
        temp = original
        helper(i+1,j,board,output,temp, dim)
        return output
```

optimized:

```
def print_paths(board):
    output_list = []
    temp_str_list = []
    search(0,0,board,temp_str_list,output_list)
    return output_list    

def search(i,j,board,temp_str_list,output_list):
    rows = len(board)
    cols = len(board[0])
    if i > rows - 1 or j > cols -1:
        return
    temp_str_list.append(board[i][j])
    if i == rows - 1 and j == cols - 1:
        output_list.append("".join(temp_str_list))
        temp_str_list.pop()
        return
  
    search(i+1,j,board,temp_str_list,output_list); # Search Down
    search(i,j+1,board,temp_str_list,output_list); # Search Right
    temp_str_list.pop() # Un-Mark
```



