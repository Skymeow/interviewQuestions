interviewQuestions

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

#### solution:

```

```



