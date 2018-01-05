interviewQuestions

### What would be the time complexity of a method that uses the`binary search algorithm`to check if an integer exists in a sorted list?

O\(logN\)

### The worst-case scenarios for BST's all involve a completely unbalanced tree, which degenerates into a singly-linked list. For example, if you just add 1, 2, 3, 4, 5 in that order to a simple \(non-self-balancing\) BST implementation, then all your nodes will only have a right child. You then do not get the "halving at every step" characteristic that gives BST's their power.

In this worst-case scenario:

* **access is O\(n\)**
* **search is O\(n\)**
* **insertion is O\(n\)**
* **deletion is O\(n\)** 



