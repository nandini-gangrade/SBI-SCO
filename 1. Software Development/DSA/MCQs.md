### **1. Arrays**

**1. Which of the following is the correct index range for an array in Java?**
a) 0 to n  
b) 1 to n  
c) 0 to n-1  
d) -1 to n-1  

**Correct Option**: c) 0 to n-1  
**Explanation**: In Java, arrays are zero-indexed, meaning the index range is from 0 to `n-1`, where `n` is the size of the array.

**2. What is the time complexity of accessing an element in an array?**  
a) O(n)  
b) O(1)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(1)  
**Explanation**: Accessing an element in an array is a constant-time operation, as the index directly points to the memory address of the element.

---

### **2. Linked Lists**

**3. What is a major disadvantage of using a linked list?**  
a) Difficulty in resizing  
b) Memory waste due to pointers  
c) Easy to search for elements  
d) Fixed size  

**Correct Option**: b) Memory waste due to pointers  
**Explanation**: Linked lists use additional memory to store pointers along with the data, causing memory overhead.

**4. In a singly linked list, how can you access the last element?**  
a) Directly using the index  
b) By traversing the entire list  
c) By using a pointer to the last node  
d) It is not possible to access the last element  

**Correct Option**: b) By traversing the entire list  
**Explanation**: In a singly linked list, to access the last element, you must traverse the list from the head to the last node.

---

### **3. Stacks**

**5. Which of the following operations is not supported in a stack?**  
a) Push  
b) Pop  
c) Peek  
d) Search (without popping elements)  

**Correct Option**: d) Search (without popping elements)  
**Explanation**: A stack supports LIFO (Last In, First Out) operations like push, pop, and peek. Searching without popping elements is not directly supported.

**6. What is the time complexity of the `push` operation in a stack?**  
a) O(n)  
b) O(1)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(1)  
**Explanation**: Pushing an element onto a stack is a constant time operation, as the element is added to the top.

---

### **4. Queues**

**7. What is the time complexity for enqueue and dequeue operations in a queue?**  
a) O(n)  
b) O(1)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(1)  
**Explanation**: Both enqueue and dequeue operations in a queue are constant-time operations, as elements are added to or removed from the front and rear.

**8. Which of the following data structures is used to implement a queue?**  
a) Array  
b) Linked list  
c) Stack  
d) Both a and b  

**Correct Option**: d) Both a and b  
**Explanation**: A queue can be implemented using both arrays and linked lists.

---

### **5. Binary Tree**

**9. What is the maximum number of children a node in a binary tree can have?**  
a) 1  
b) 2  
c) 3  
d) Infinite  

**Correct Option**: b) 2  
**Explanation**: A binary tree is a tree where each node has at most two children: a left child and a right child.

**10. What is the time complexity of accessing an element in a binary search tree (BST)?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: b) O(log n)  
**Explanation**: In a balanced BST, accessing an element (search) takes `O(log n)` time, as the tree is halved at each step.

---

### **6. Binary Search Tree (BST)**

**11. In a Binary Search Tree (BST), what is the property of the left child node?**  
a) It is greater than the parent node  
b) It is smaller than the parent node  
c) It is equal to the parent node  
d) It can be anything  

**Correct Option**: b) It is smaller than the parent node  
**Explanation**: In a BST, the left child node is always smaller than its parent node, while the right child node is always greater.

**12. What is the time complexity for inserting an element in a binary search tree (BST)?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: b) O(log n)  
**Explanation**: In a balanced BST, inserting an element involves traversing the tree from the root to the appropriate leaf, which takes `O(log n)` time.

---

### **7. Heaps**

**13. What property does a Min-Heap maintain?**  
a) The root is the largest element  
b) The root is the smallest element  
c) All elements are in sorted order  
d) It has no special property  

**Correct Option**: b) The root is the smallest element  
**Explanation**: In a Min-Heap, the value of each parent node is less than or equal to the values of its children, ensuring that the root is the smallest element.

**14. What is the time complexity of extracting the minimum element from a Min-Heap?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n log n)  

**Correct Option**: b) O(log n)  
**Explanation**: Extracting the minimum element from a Min-Heap requires removing the root and then reheapifying the heap, which takes `O(log n)` time.

---

### **8. Hashing**

**15. What is the main idea behind hashing?**  
a) Storing elements in a tree structure  
b) Using a hash function to map data to a fixed-size table  
c) Storing elements sequentially  
d) Storing elements in an array  

**Correct Option**: b) Using a hash function to map data to a fixed-size table  
**Explanation**: Hashing uses a hash function to map data to a fixed-size table, called a hash table, allowing for efficient access and retrieval.

**16. What is a common issue with hashing?**  
a) Large space usage  
b) Collisions  
c) Slow data access  
d) Fixed-size storage  

**Correct Option**: b) Collisions  
**Explanation**: A collision occurs when two distinct keys hash to the same index. It needs to be handled properly using methods like chaining or open addressing.

---

### **9. Recursion**

**17. Which of the following is a key characteristic of recursive functions?**  
a) They don’t have a base case  
b) They call themselves  
c) They use iteration  
d) They only work with arrays  

**Correct Option**: b) They call themselves  
**Explanation**: A recursive function calls itself with modified parameters, and it needs a base case to terminate.

**18. What is the time complexity of the recursive Fibonacci function?**  
a) O(1)  
b) O(n)  
c) O(n^2)  
d) O(2^n)  

**Correct Option**: d) O(2^n)  
**Explanation**: The recursive Fibonacci function exhibits exponential time complexity due to repeated subproblem calculations.

---

### **10. Tree Traversal (DFS & BFS)**

**19. What is the traversal order for **pre-order** traversal in a binary tree?**  
a) Left, Right, Root  
b) Root, Left, Right  
c) Left, Root, Right  
d) Right, Left, Root  

**Correct Option**: b) Root, Left, Right  
**Explanation**: In pre-order traversal, the root is visited first, then the left subtree, and finally the right subtree.

**20. What is the time complexity of BFS for traversing a graph?**  
a) O(n)  
b) O(V + E)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(V + E)  
**Explanation**: In BFS, the algorithm explores all vertices (`V`) and edges (`E`) of the graph, which results in time complexity of `O(V + E)`.

---

### **11. Sorting Algorithms**

**21. Which sorting algorithm has the best average time complexity?**  
a) Bubble Sort  
b) Merge Sort  
c) Quick Sort  
d) Selection Sort  

**Correct Option**: b) Merge Sort  
**Explanation**: Merge Sort has an average time complexity of `O(n log n)`, which is better than the `O(n^2)` average complexity of Bubble Sort and Selection Sort.

**22. What is the time complexity of QuickSort in the worst case?**  
a) O(n log n)  
b) O(log n)  


c) O(n^2)  
d) O(n)  

**Correct Option**: c) O(n^2)  
**Explanation**: In the worst case, QuickSort's time complexity becomes `O(n^2)` when the pivot chosen is the smallest or largest element in the array.

---

Continuing from the previous set, here are **more MCQs** on **Data Structures and Algorithms**:

---

### **12. Searching Algorithms**

**23. What is the time complexity of a binary search algorithm?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: c) O(log n)  
**Explanation**: Binary search splits the search space in half at each step, resulting in a time complexity of `O(log n)` for a sorted array.

**24. What is the primary requirement for applying binary search?**  
a) The list must be sorted  
b) The list must have unique elements  
c) The list must be unsorted  
d) The list must be a tree  

**Correct Option**: a) The list must be sorted  
**Explanation**: Binary search only works on sorted lists. It eliminates half of the elements with each comparison, so the list must be in order.

---

### **13. Dynamic Programming**

**25. Which of the following is true about dynamic programming (DP)?**  
a) DP is used to solve problems by breaking them into simpler subproblems and storing the results of overlapping subproblems  
b) DP only works for problems with no overlapping subproblems  
c) DP is used to solve problems with optimal substructure but without overlapping subproblems  
d) DP always leads to better time complexity than greedy algorithms  

**Correct Option**: a) DP is used to solve problems by breaking them into simpler subproblems and storing the results of overlapping subproblems  
**Explanation**: DP is a technique that solves problems by dividing them into simpler subproblems and using memoization or tabulation to store results of overlapping subproblems.

**26. What is the time complexity of the Fibonacci sequence using dynamic programming (tabulation)?**  
a) O(2^n)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(n)  
**Explanation**: Using dynamic programming to compute Fibonacci numbers via tabulation allows the solution to be computed in linear time, `O(n)`.

---

### **14. Graph Algorithms**

**27. What is the time complexity of DFS for a graph with V vertices and E edges?**  
a) O(V)  
b) O(V + E)  
c) O(E)  
d) O(V^2)  

**Correct Option**: b) O(V + E)  
**Explanation**: In DFS, each vertex and each edge of the graph is visited at most once, resulting in a time complexity of `O(V + E)`.

**28. Which algorithm is used to find the shortest path in a graph with non-negative edge weights?**  
a) Bellman-Ford  
b) Dijkstra’s Algorithm  
c) Floyd-Warshall  
d) Prim’s Algorithm  

**Correct Option**: b) Dijkstra’s Algorithm  
**Explanation**: Dijkstra’s algorithm is used to find the shortest path in a graph with non-negative edge weights by greedily selecting the minimum distance vertex at each step.

---

### **15. Recursion & Backtracking**

**29. Which of the following problems can be solved using backtracking?**  
a) Sorting an array  
b) Finding the shortest path in a graph  
c) Solving the N-Queens problem  
d) Performing binary search on an array  

**Correct Option**: c) Solving the N-Queens problem  
**Explanation**: Backtracking is a technique used for problems like N-Queens, where we try all possible configurations and backtrack when we find an invalid one.

**30. What is the primary difference between recursion and iteration?**  
a) Recursion involves repeating the same process until a condition is met, while iteration involves breaking the problem into simpler parts.  
b) Recursion involves function calls, while iteration involves looping.  
c) Recursion has better time complexity than iteration.  
d) Recursion is used for sorting, while iteration is used for searching.  

**Correct Option**: b) Recursion involves function calls, while iteration involves looping.  
**Explanation**: Recursion involves a function calling itself, while iteration uses looping structures (like `for` or `while`) to repeat tasks.

---

### **16. Sorting Algorithms**

**31. Which of the following sorting algorithms is based on the divide and conquer approach?**  
a) Bubble Sort  
b) Merge Sort  
c) Selection Sort  
d) Insertion Sort  

**Correct Option**: b) Merge Sort  
**Explanation**: Merge Sort is a divide-and-conquer algorithm where the list is divided into two halves, each sorted recursively, and then merged.

**32. Which sorting algorithm is best for sorting a small array of elements?**  
a) QuickSort  
b) MergeSort  
c) Insertion Sort  
d) HeapSort  

**Correct Option**: c) Insertion Sort  
**Explanation**: Insertion Sort works well for small arrays as it has a small constant factor in its time complexity and performs well when the list is nearly sorted.

---

### **17. Heaps**

**33. Which of the following is true for a Max-Heap?**  
a) The root is the largest element.  
b) The root is the smallest element.  
c) The tree is always balanced.  
d) It is a sorted tree.  

**Correct Option**: a) The root is the largest element.  
**Explanation**: In a Max-Heap, the root contains the largest element, and each parent node is greater than or equal to its children.

**34. What is the time complexity of inserting an element into a heap?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n log n)  

**Correct Option**: b) O(log n)  
**Explanation**: Insertion in a heap involves adding an element and then reheapifying, which takes logarithmic time, `O(log n)`.

---

### **18. Binary Search Tree (BST)**

**35. Which of the following is true about the in-order traversal of a Binary Search Tree (BST)?**  
a) It visits nodes in ascending order.  
b) It visits nodes in descending order.  
c) It visits nodes in random order.  
d) It doesn’t visit all nodes.  

**Correct Option**: a) It visits nodes in ascending order.  
**Explanation**: In-order traversal of a BST visits the nodes in ascending order of their values.

**36. What is the time complexity of searching for an element in a balanced Binary Search Tree (BST)?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n log n)  

**Correct Option**: b) O(log n)  
**Explanation**: In a balanced BST, the tree height is logarithmic (`O(log n)`), so searching for an element takes logarithmic time.

---

### **19. Hashing**

**37. Which of the following is a collision resolution technique used in hashing?**  
a) Binary Search  
b) Chaining  
c) Sorting  
d) Merge Sort  

**Correct Option**: b) Chaining  
**Explanation**: Chaining is a collision resolution technique where each bucket of the hash table stores a linked list of elements that hash to the same index.

**38. What is the time complexity of searching for an element in a hash table with proper collision handling?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: In a well-implemented hash table with proper collision handling, search operations can be performed in constant time, `O(1)`.

---

### **20. Recursion**

**39. Which of the following is the base case for the recursive factorial function?**  
a) n == 1  
b) n == 0  
c) n == n-1  
d) n == 2  

**Correct Option**: b) n == 0  
**Explanation**: The base case for the recursive factorial function is `n == 0`, where `factorial(0) = 1`.

**40. Which of the following statements is true for recursion?**  
a) Recursion uses explicit iteration.  
b) Recursion always consumes more memory than iteration.  
c) Recursion has no use in algorithms.  
d) Recursion can replace iteration in many algorithms.  

**Correct Option**: d) Recursion can replace iteration in many algorithms.  
**Explanation**: Recursion can be used instead of iteration in many algorithms, especially when the problem involves breaking it down into subproblems.

---

### **21. Arrays**

**41. Which of the following is the time complexity of accessing an element in an array?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: a) O(1)  
**Explanation**: Arrays allow direct access to elements via index, so accessing any element takes constant time, `O(1)`.

**42. What is the primary disadvantage of using an array to implement a stack?**  
a) It is difficult to access elements.  
b) It requires resizing and shifting elements.  
c) It can only store one type of data.  
d) It doesn’t allow dynamic memory allocation.  

**Correct Option**: b) It requires resizing and shifting elements.  
**Explanation**: If the array grows or shrinks, elements might need to be shifted, which results in O(n) operations for insertion or deletion in some cases.

---

### **22. Linked Lists**

**43. What is the time complexity of inserting an element at the beginning of a singly linked list?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: a) O(1)  
**Explanation**: Inserting at the beginning of a singly linked list takes constant time, `O(1)`, because we just need to update the head pointer.

**44. What is the time complexity of searching for an element in an unsorted linked list?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: c) O(n)  
**Explanation**: In an unsorted linked list, we need to traverse each element to find the target, so the time complexity is linear, `O(n)`.

---

### **23. Stacks**

**45. Which data structure uses the LIFO (Last In, First Out) principle?**  
a) Queue  
b) Linked List  
c) Stack  
d) Tree  

**Correct Option**: c) Stack  
**Explanation**: A stack follows the LIFO principle, where the last element added is the first one to be removed.

**46. What is the time complexity of pushing an element onto a stack?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: a) O(1)  
**Explanation**: Inserting an element onto a stack takes constant time, `O(1)`, since it only involves adding the element to the top of the stack.

---

### **24. Queues**

**47. Which data structure follows the FIFO (First In, First Out) principle?**  
a) Stack  
b) Queue  
c) Array  
d) Tree  

**Correct Option**: b) Queue  
**Explanation**: A queue follows the FIFO principle, where the first element inserted is the first one to be removed.

**48. What is the time complexity of enqueue operation in a queue?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: Enqueue operation (inserting an element into a queue) takes constant time, `O(1)`, assuming the queue is implemented using a linked list or dynamic array.

---

### **25. Binary Trees**

**49. What is the maximum number of nodes at level `l` of a binary tree?**  
a) 2^l  
b) 2^(l-1)  
c) l^2  
d) 2 * l  

**Correct Option**: a) 2^l  
**Explanation**: The maximum number of nodes at level `l` of a binary tree is `2^l`, as each level doubles the number of nodes.

**50. What is the time complexity of searching for an element in a binary tree with `n` nodes?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n log n)  

**Correct Option**: c) O(n)  
**Explanation**: In an unbalanced binary tree, in the worst case, we might need to visit every node to find an element, leading to a time complexity of `O(n)`.

---

### **26. Binary Search Trees (BST)**

**51. Which of the following operations on a Binary Search Tree (BST) is performed in O(log n) time in the average case?**  
a) Insertion  
b) Search  
c) Deletion  
d) All of the above  

**Correct Option**: d) All of the above  
**Explanation**: In a balanced BST, insertion, search, and deletion can all be performed in `O(log n)` time because the height of the tree is logarithmic in the number of nodes.

**52. Which traversal method of a Binary Search Tree (BST) yields the nodes in ascending order?**  
a) Pre-order  
b) In-order  
c) Post-order  
d) Level-order  

**Correct Option**: b) In-order  
**Explanation**: In-order traversal of a BST visits nodes in ascending order of their values, as it first visits the left subtree, then the root, and then the right subtree.

---

### **27. Hash Tables**

**53. What is the average time complexity of searching for an element in a hash table with separate chaining for collision resolution?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: In a hash table with separate chaining, if the load factor is low, the average time complexity for search operations is constant, `O(1)`.

**54. What is a major disadvantage of hash tables?**  
a) Hash tables require more memory than arrays.  
b) Hash tables cannot handle duplicate values.  
c) Hash tables have poor worst-case time complexity.  
d) Hash tables are inefficient for searching.  

**Correct Option**: c) Hash tables have poor worst-case time complexity.  
**Explanation**: In the worst case (e.g., if many collisions occur), the time complexity for search, insert, and delete operations can degrade to `O(n)`.

---

### **28. Recursion**

**55. Which of the following is the correct base case for the recursive function to calculate factorial?**  
a) n == 1  
b) n == 0  
c) n == 2  
d) n == n-1  

**Correct Option**: b) n == 0  
**Explanation**: The base case for calculating factorial is when `n == 0`, as `0! = 1`.

**56. What is the main issue with recursion in terms of memory usage?**  
a) Recursion can lead to stack overflow if there are too many recursive calls.  
b) Recursion uses more memory compared to iteration.  
c) Recursion is inefficient and leads to more memory usage.  
d) Recursion is not a memory-efficient approach.  

**Correct Option**: a) Recursion can lead to stack overflow if there are too many recursive calls.  
**Explanation**: Recursion consumes stack memory with each recursive call. If the recursion depth is too high, it can lead to a stack overflow.

---

### **29. Sorting Algorithms**

**57. What is the average time complexity of Merge Sort?**  
a) O(n)  
b) O(n log n)  
c) O(n^2)  
d) O(log n)  

**Correct Option**: b) O(n log n)  
**Explanation**: Merge Sort has an average time complexity of `O(n log n)` because it divides the array into halves and then merges them, which takes `O(n)` at each level of recursion.

**58. What is the best-case time complexity of QuickSort?**  
a) O(n)  
b) O(n log n)  
c) O(n^2)  
d) O(log n)  

**Correct Option**: b) O(n log n)  
**Explanation**: QuickSort’s best case occurs when the pivot divides the array into two nearly equal halves, resulting in a time complexity of `O(n log n)`.

---

### **30. Heaps**

**59. Which of the following is true about a Min-Heap?**  
a) The root is the smallest element.  
b) The root is the largest element.  
c) The tree is always balanced.  
d) It is a sorted tree.  

**Correct Option**: a) The root is the smallest element.  
**Explanation**: In a Min-Heap, the root contains the smallest element, and each parent node is smaller than its children.

**60. What is the time complexity of heapifying an element in a binary heap?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n log n)  

**Correct Option**: b) O(log n)  
**Explanation**: Heapifying an element involves comparing it with its parent and children, which takes logarithmic time, `O(log n)`.

---

### **31. Arrays - Advanced Concepts**

**61. What is the time complexity of finding the maximum element in an unsorted array?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: b) O(n)  
**Explanation**: To find the maximum element in an unsorted array, we must scan through every element, which results in a time complexity of O(n).

**62. What is the space complexity of a dynamic array?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(n)  
**Explanation**: A dynamic array stores elements in contiguous memory locations, so the space complexity is O(n), where n is the number of elements.

---

### **32. Linked Lists - Advanced Concepts**

**63. What is the time complexity for deleting a node in a doubly linked list given a pointer to the node to be deleted?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: In a doubly linked list, if we are given a pointer to the node to delete, we can directly update the previous and next pointers of the adjacent nodes, making the operation take constant time, O(1).

**64. Which of the following is the correct order of operations for reversing a singly linked list?**  
a) Traverse, Insert at front, Change pointers  
b) Change pointers, Traverse, Insert at front  
c) Insert at front, Traverse, Change pointers  
d) Traverse, Change pointers, Insert at front  

**Correct Option**: a) Traverse, Insert at front, Change pointers  
**Explanation**: To reverse a singly linked list, we traverse the list, and for each node, we insert it at the front and change the node pointers accordingly.

---

### **33. Stacks - Advanced Concepts**

**65. Which of the following is the time complexity of the "peek" operation in a stack?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: The "peek" operation (returning the top element of the stack) takes constant time, O(1), since the top element is directly accessible.

**66. What is the time complexity of checking if a stack is empty?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: a) O(1)  
**Explanation**: Checking if a stack is empty takes constant time, O(1), because we can directly check if the size of the stack is zero.

---

### **34. Queues - Advanced Concepts**

**67. In a circular queue, what is the time complexity for enqueuing an element?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: a) O(1)  
**Explanation**: In a circular queue, the enqueue operation can be done in constant time, O(1), since we use the modulo operation to wrap around the queue when the rear reaches the end.

**68. In a circular queue, how can we prevent the situation where the queue appears full even though there is space available?**  
a) Using a counter for the number of elements in the queue.  
b) Using a dynamic array for resizing.  
c) Allowing overflow beyond the queue’s capacity.  
d) None of the above.  

**Correct Option**: a) Using a counter for the number of elements in the queue.  
**Explanation**: In a circular queue, the front and rear pointers could meet even when there’s space. Using a counter to track the number of elements helps to differentiate between a full and empty queue.

---

### **35. Binary Trees - Advanced Concepts**

**69. What is the time complexity of inserting a node into a Binary Search Tree (BST) in the worst case?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n log n)  

**Correct Option**: c) O(n)  
**Explanation**: In the worst case, if the BST is unbalanced (like a linked list), insertion will require traversing all the way from the root to the leaf node, resulting in a time complexity of O(n).

**70. What is the space complexity of storing a complete binary tree?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: c) O(n)  
**Explanation**: A complete binary tree requires space proportional to the number of nodes, i.e., O(n), as each node is stored in memory.

---

### **36. Binary Search Trees (BST) - Advanced Concepts**

**71. What is the time complexity of finding the minimum value in a Binary Search Tree (BST)?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n log n)  

**Correct Option**: b) O(log n)  
**Explanation**: In a balanced BST, the minimum value is found by repeatedly following the left child pointers, which takes logarithmic time, O(log n).

**72. Which traversal method is typically used to delete all nodes of a Binary Search Tree (BST)?**  
a) Pre-order  
b) In-order  
c) Post-order  
d) Level-order  

**Correct Option**: c) Post-order  
**Explanation**: In post-order traversal, the node is deleted after its children have been visited, ensuring that no child node is left with references to a parent node.

---

### **37. Hashing - Advanced Concepts**

**73. What is a common problem in hashing, and how can it be resolved?**  
a) Collision, using separate chaining or open addressing.  
b) Redundancy, using perfect hashing.  
c) Memory overflow, using dynamic arrays.  
d) Search inefficiency, using AVL trees.  

**Correct Option**: a) Collision, using separate chaining or open addressing.  
**Explanation**: Collisions in a hash table occur when two keys hash to the same index. This can be resolved using separate chaining (linked lists) or open addressing (probing).

**74. What is the time complexity of searching for an element in a hash table using linear probing for collision resolution?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: c) O(n)  
**Explanation**: In the worst case, linear probing may require scanning all the entries, leading to a time complexity of O(n).

---

### **38. Recursion - Advanced Concepts**

**75. What is the time complexity of the recursive Fibonacci function?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(2^n)  

**Correct Option**: d) O(2^n)  
**Explanation**: The recursive Fibonacci function has exponential time complexity, O(2^n), because it repeatedly recalculates the same subproblems.

**76. Which of the following can be used to optimize recursive Fibonacci calculations?**  
a) Memoization  
b) Tabulation  
c) Both a and b  
d) None of the above  

**Correct Option**: c) Both a and b  
**Explanation**: Both memoization (caching results) and tabulation (iterative dynamic programming) can optimize recursive Fibonacci calculations, reducing the time complexity to O(n).

---

### **39. Sorting Algorithms - Advanced Concepts**

**77. Which of the following is a non-comparison-based sorting algorithm?**  
a) QuickSort  
b) MergeSort  
c) HeapSort  
d) Counting Sort  

**Correct Option**: d) Counting Sort  
**Explanation**: Counting Sort is a non-comparison-based sorting algorithm that uses the frequency of elements to determine their position in the sorted array.

**78. What is the best-case time complexity of Bubble Sort?**  
a) O(n)  
b) O(n^2)  
c) O(log n)  
d) O(1)  

**Correct Option**: a) O(n)  
**Explanation**: In the best case, when the array is already sorted, Bubble Sort will only require one pass through the array to check if it's sorted, making the time complexity O(n).

---

### **40. Heaps - Advanced Concepts**

**79. Which of the following is true for a Min-Heap?**  
a) The parent node is smaller than both children nodes.  
b) The parent node is larger than both children nodes.  
c) The root node is always the maximum element.  
d) The heap is always a complete binary tree.  

**Correct Option**: a) The parent node is smaller than both children nodes.  
**Explanation**: In a Min-Heap, the parent node is always smaller than its children, ensuring the smallest element is at the root.

**80. What is the time complexity of extracting the root from a Min-Heap?**  
a) O(1)  
b) O(log n)

  
c) O(n)  
d) O(n log n)  

**Correct Option**: b) O(log n)  
**Explanation**: Extracting the root from a Min-Heap involves removing the root and then reheapifying, which takes logarithmic time, O(log n).

---

### **41. Arrays - Intermediate Concepts**

**81. What is the time complexity of accessing an element at a specific index in an array?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: In arrays, elements are stored in contiguous memory locations. Accessing an element at a specific index is done in constant time, O(1).

**82. Which of the following array operations can be done in O(n) time complexity?**  
a) Inserting at the beginning  
b) Accessing an element at an index  
c) Sorting  
d) Deleting an element at the end  

**Correct Option**: a) Inserting at the beginning  
**Explanation**: Inserting an element at the beginning of an array requires shifting all the existing elements, which results in O(n) time complexity.

---

### **42. Linked Lists - Intermediate Concepts**

**83. What is the time complexity of deleting the head node of a singly linked list?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: Deleting the head node of a singly linked list is done in constant time, O(1), because we just need to change the head pointer to the next node.

**84. What is the space complexity of a doubly linked list?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(n)  
**Explanation**: A doubly linked list stores additional pointers (previous and next) for each node, so the space complexity is O(n), where n is the number of elements.

---

### **43. Stacks - Intermediate Concepts**

**85. Which of the following operations can be done in constant time, O(1), in a stack?**  
a) Push  
b) Pop  
c) Peek  
d) All of the above  

**Correct Option**: d) All of the above  
**Explanation**: All three operations in a stack (push, pop, peek) are done in constant time, O(1), because they only involve adding/removing the top element or inspecting it.

**86. What is the space complexity of a stack implemented using a linked list?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(n)  
**Explanation**: In a stack implemented with a linked list, the space complexity is O(n), where n is the number of elements in the stack.

---

### **44. Queues - Intermediate Concepts**

**87. What is the time complexity of dequeue operation in a queue implemented using a linked list?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: a) O(1)  
**Explanation**: Dequeue operation in a queue using a linked list involves removing the front node, which can be done in constant time, O(1).

**88. Which of the following is true for a priority queue?**  
a) It stores elements in FIFO order.  
b) It stores elements in LIFO order.  
c) It stores elements in a sorted order based on their priority.  
d) It stores elements in unsorted order.  

**Correct Option**: c) It stores elements in a sorted order based on their priority.  
**Explanation**: A priority queue ensures that the element with the highest priority is always at the front of the queue.

---

### **45. Binary Trees - Intermediate Concepts**

**89. What is the height of a perfect binary tree with 7 nodes?**  
a) 2  
b) 3  
c) 4  
d) 5  

**Correct Option**: b) 3  
**Explanation**: In a perfect binary tree, all the levels are fully filled. A perfect binary tree with 7 nodes has a height of 3, because a perfect binary tree with 3 levels will have 7 nodes.

**90. What is the time complexity of finding the height of a binary tree?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n^2)  

**Correct Option**: b) O(n)  
**Explanation**: The height of a binary tree is found by traversing all the nodes, so the time complexity is O(n), where n is the number of nodes in the tree.

---

### **46. Binary Search Trees (BST) - Intermediate Concepts**

**91. What is the worst-case time complexity of searching in an unbalanced binary search tree?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: b) O(n)  
**Explanation**: In the worst case, an unbalanced BST may resemble a linked list, so searching may require traversing all n nodes, resulting in O(n) time complexity.

**92. Which of the following is NOT a property of a binary search tree?**  
a) Left child is smaller than the parent node.  
b) Right child is larger than the parent node.  
c) In-order traversal gives elements in sorted order.  
d) The tree is always balanced.  

**Correct Option**: d) The tree is always balanced.  
**Explanation**: A BST does not require the tree to be balanced. In fact, if not balanced, the tree can become inefficient with operations like searching, insertion, and deletion.

---

### **47. Heaps - Intermediate Concepts**

**93. What is the time complexity of building a heap from an unsorted array?**  
a) O(n)  
b) O(log n)  
c) O(n log n)  
d) O(n^2)  

**Correct Option**: a) O(n)  
**Explanation**: Building a heap from an unsorted array involves performing heapify operations on all non-leaf nodes, which can be done in O(n) time.

**94. In a max-heap, which of the following is true?**  
a) The parent node is smaller than its children.  
b) The parent node is equal to its children.  
c) The parent node is greater than its children.  
d) The heap is not a complete binary tree.  

**Correct Option**: c) The parent node is greater than its children.  
**Explanation**: In a max-heap, each parent node must be greater than or equal to its children, ensuring the largest element is at the root.

---

### **48. Hashing - Intermediate Concepts**

**95. What is the time complexity of searching for an element in a hash table using chaining for collision resolution?**  
a) O(1)  
b) O(log n)  
c) O(n)  
d) O(n^2)  

**Correct Option**: c) O(n)  
**Explanation**: In the worst case, when all elements hash to the same bucket (i.e., a collision), the search will require traversing the linked list, which takes O(n) time.

**96. Which of the following is an ideal hash function?**  
a) A hash function that minimizes collisions.  
b) A hash function that produces evenly distributed keys.  
c) A hash function that maximizes the number of buckets.  
d) A hash function that increases the size of the hash table.  

**Correct Option**: b) A hash function that produces evenly distributed keys.  
**Explanation**: An ideal hash function minimizes collisions and ensures that keys are distributed evenly across the hash table.

---

### **49. Recursion - Intermediate Concepts**

**97. What is the time complexity of the recursive function for the Tower of Hanoi problem?**  
a) O(1)  
b) O(n)  
c) O(n^2)  
d) O(2^n)  

**Correct Option**: d) O(2^n)  
**Explanation**: The Tower of Hanoi problem has an exponential time complexity, O(2^n), because for each disk, the number of moves doubles.

**98. Which of the following problems can be solved using recursion?**  
a) Finding the factorial of a number  
b) Sorting an array  
c) Searching in a binary tree  
d) All of the above  

**Correct Option**: d) All of the above  
**Explanation**: All of these problems can be solved using recursion, as recursion is often used for problems involving repetitive or nested sub-problems.

---

### **50. Sorting Algorithms - Intermediate Concepts**

**99. Which sorting algorithm has the best average-case time complexity?**  
a) QuickSort  
b) MergeSort  
c) HeapSort  
d) BubbleSort  

**Correct Option**: b) MergeSort  
**Explanation**: MergeSort has an average-case time complexity of O(n log n), which is better than QuickSort’s average O(n^2) in some cases.

**100. What is the space complexity of QuickSort?**  
a) O(1)  
b) O(n)  
c) O(log n)  
d) O(n log n)  

**Correct Option**: c) O(log n)  
**Explanation**: QuickSort has a space complexity of O(log n) due to the recursive function calls that require additional stack space.

