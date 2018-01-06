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



