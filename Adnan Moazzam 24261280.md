Unit 1: Introduction to Python and Data Structures

1. Programming in Python

Python is an interpreted, high-level, general-purpose programming language that emphasizes readability and simplicity in coding. Its syntax is designed to be clear and easy to understand, making it ideal for both beginners and experienced developers. Python supports multiple programming paradigms, including procedural, object-oriented, and functional programming.

Python's basic syntax involves defining variables, using data types, and writing functions. For example, variables in Python can store data such as integers, strings, lists, and dictionaries:

Variables: Variables are used to store data in Python. For example, x = 5 stores the integer value 5 in the variable x.
Functions: Functions allow us to group related code into a block that can be executed when called. For instance:

Example -
def add(a, b):
    return a + b
(This function add takes two parameters a and b and returns their sum.)

Python also includes a variety of built-in data types such as integers, strings, lists, tuples, sets, and dictionaries, which help organize and manipulate data efficiently.

2. Basic Data Structures

Data structures are ways to organize and store data so that they can be accessed and manipulated efficiently. In Python, some of the basic data structures include stacks, queues, linked lists, trees, and hash tables.

- Stacks: A stack is a linear data structure that follows the Last In First Out (LIFO) principle, meaning the last element added to the stack is the first to be removed. In Python, stacks can be implemented using lists, where the append() method is used to push elements onto the stack, and the pop() method is used to remove the top element.
Example:
stack.append(1)  # push 1 onto the stack
stack.append(2)  # push 2 onto the stack
stack.pop()      # pops 2 from the stack

- Queues: A queue is another linear data structure, but it follows the First In First Out (FIFO) principle, meaning the first element added is the first to be removed. In Python, a queue can be implemented using a list or deque from the collections module. The append() method is used to enqueue an element, and the popleft() method is used to dequeue an element. For example:

Example : 
from collections import deque
queue = deque()
queue.append(1)  # enqueue 1 into the queue
queue.append(2)  # enqueue 2 into the queue
queue.popleft()  # dequeue 1 from the queue

- Linked Lists: A linked list is a linear data structure in which elements (called nodes) are stored in a sequence where each node points to the next node. It consists of a sequence of nodes, where each node contains two parts: the data and a reference (or link) to the next node. Here's a simple implementation of a singly linked list:

Example:
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

- Trees: A tree is a hierarchical data structure consisting of nodes, where each node contains a value and pointers to its child nodes. A binary tree is a type of tree where each node has at most two children, often referred to as the left and right child.

Example:
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

- Hash Tables: A hash table is a data structure that stores key-value pairs and allows for fast access to values based on their corresponding keys. The key is hashed to determine the index in an underlying array where the value is stored. In Python, hash tables are implemented as dictionaries (dict). 

Example:
hash_table = {}
hash_table["name"] = "Alice"
hash_table["age"] = 25
value = hash_table["name"]  # retrieves "Alice"

3. Search Algorithms

- Linear Search: Linear search is a straightforward search algorithm where each element of the array or list is checked sequentially until the target element is found or the entire list has been searched. If the target is found, its index is returned; otherwise, -1 is returned. The time complexity of linear search is O(n), where n is the number of elements in the array.

Example:
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1

- Binary Search: Binary search is a more efficient search algorithm used on sorted arrays. The array is repeatedly divided in half, and the middle element is checked to see if it is the target. If the target is smaller than the middle element, the search continues in the left half of the array; otherwise, it continues in the right half. Binary search has a time complexity of O(log n), which makes it much faster than linear search for large datasets.

Example:

def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

4. Sorting Algorithms

Sorting algorithms are used to arrange data in a specific order, typically in ascending or descending order. Below are a few common sorting algorithms.

- Selection Sort: Selection sort is an in-place, comparison-based sorting algorithm. It works by repeatedly finding the smallest element from the unsorted part of the list and swapping it with the first unsorted element. The algorithm has a time complexity of O(n²), where n is the number of elements in the array.

Example:

def selection_sort(arr):
    for i in range(len(arr)):
        min_idx = i
        for j in range(i + 1, len(arr)):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]

- Bubble Sort: Bubble sort works by repeatedly stepping through the list, comparing adjacent elements, and swapping them if they are in the wrong order. The process is repeated until the list is sorted. Like selection sort, bubble sort has a time complexity of O(n²), making it inefficient for large datasets.

Example:
def bubble_sort(arr):
    for i in range(len(arr) - 1):
        for j in range(len(arr) - 1 - i):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
        
- Insertion Sort: Insertion sort builds the final sorted array one element at a time by inserting each element into its correct position within the sorted portion of the array. Like the previous algorithms, insertion sort has a time complexity of O(n²) in the worst case but can be more efficient for nearly sorted data.

Example :
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key

- Merge Sort: Merge sort is a divide-and-conquer algorithm that divides the array into two halves, recursively sorts each half, and then merges the two halves into a sorted array. Merge sort has a time complexity of O(n log n), which makes it more efficient than the simpler algorithms for large datasets.

Example:
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]
        merge_sort(left_half)
        merge_sort(right_half)
        i = j = k = 0
        while i < len(left_half) and j < len(right_half):
            if left_half[i] < right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1
        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1
        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1

Quick Sort: Quick sort is another divide-and-conquer sorting algorithm that selects a pivot element from the array and partitions the other elements into two sub-arrays according to whether they are smaller or greater than the pivot. The sub-arrays are then sorted recursively. On average, quick sort has a time complexity of O(n


