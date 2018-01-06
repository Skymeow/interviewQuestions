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

### Int to binary:

```
def dec_to_bin(number):
   return dec_to_bin(number/2) + str(number%2) if number > 1 else str(number)

```



