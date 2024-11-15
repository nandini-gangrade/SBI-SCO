### **1. Arrays**

#### **Question**: How do you find the second largest element in an array?

**Approach**:
- Initialize two variables `largest` and `secondLargest` to keep track of the largest and second-largest values, respectively.
- Iterate through the array and update the values based on the current element:
  - If the current element is greater than `largest`, then update `secondLargest` to `largest` and `largest` to the current element.
  - If the current element is greater than `secondLargest` but not equal to `largest`, update `secondLargest`.

**Logic & Intuition**:
- **Time Complexity**: `O(n)` where `n` is the size of the array.
- **Space Complexity**: `O(1)` as we are only using a couple of extra variables.
  
**Code**:
```java
int findSecondLargest(int[] arr) {
    int largest = Integer.MIN_VALUE, secondLargest = Integer.MIN_VALUE;
    for (int num : arr) {
        if (num > largest) {
            secondLargest = largest;
            largest = num;
        } else if (num > secondLargest && num != largest) {
            secondLargest = num;
        }
    }
    return secondLargest;
}
```
- **Explanation**: This method finds the largest element and then the second largest in one pass.

---

#### **Question**: Write a function to rotate an array by `k` positions.

**Approach**:
- To rotate the array, we reverse the entire array, then reverse the first `k` elements, and then reverse the remaining part.
- The reason for reversing the array is that it essentially brings the desired elements to the front.

**Logic & Intuition**:
- **Time Complexity**: `O(n)`, where `n` is the size of the array.
- **Space Complexity**: `O(1)` as we perform all operations in-place.

**Code**:
```java
void rotateArray(int[] arr, int k) {
    int n = arr.length;
    k = k % n; // Handle if k > n
    reverse(arr, 0, n - 1);
    reverse(arr, 0, k - 1);
    reverse(arr, k, n - 1);
}

void reverse(int[] arr, int start, int end) {
    while (start < end) {
        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        start++;
        end--;
    }
}
```
- **Explanation**: By reversing different parts of the array, we shift the elements in the desired direction efficiently.

---

### **2. Linked List**

#### **Question**: How do you reverse a singly linked list?

**Approach**:
- Use three pointers: `prev`, `current`, and `next`.
- Traverse through the linked list, and for each node, reverse its `next` pointer to point to `prev`.
- Move all pointers ahead by one step, continuing until the entire list is reversed.

**Logic & Intuition**:
- **Time Complexity**: `O(n)` where `n` is the number of nodes.
- **Space Complexity**: `O(1)` as no extra data structures are used.

**Code**:
```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

Node reverseLinkedList(Node head) {
    Node prev = null, current = head, next = null;
    while (current != null) {
        next = current.next; // Save the next node
        current.next = prev; // Reverse the link
        prev = current; // Move prev to current
        current = next; // Move current to next
    }
    return prev; // New head
}
```
- **Explanation**: As we traverse the list, we keep reversing the direction of the `next` pointers, effectively flipping the list.

---

#### **Question**: How do you detect a cycle in a linked list?

**Approach**:
- Use **Floyd’s Cycle Detection Algorithm**, also known as **Tortoise and Hare**. Use two pointers: `slow` (moves one step at a time) and `fast` (moves two steps at a time).
- If the list contains a cycle, `slow` and `fast` will eventually meet; otherwise, `fast` will reach the end (`null`).

**Logic & Intuition**:
- **Time Complexity**: `O(n)` where `n` is the number of nodes.
- **Space Complexity**: `O(1)` as only two pointers are used.

**Code**:
```java
boolean hasCycle(Node head) {
    Node slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
        if (slow == fast) return true; // Cycle detected
    }
    return false;
}
```
- **Explanation**: The slow pointer moves one step and the fast pointer moves two steps. If there's a cycle, the fast pointer will eventually "lap" the slow pointer.

---

### **3. Stack**

#### **Question**: How do you implement a stack using an array?

**Approach**:
- Implement basic stack operations such as `push`, `pop`, and `peek` using an array.
- **Push** operation adds an element to the top of the stack, while **Pop** removes the element from the top.
- **Peek** gives the value of the top element without removing it.

**Logic & Intuition**:
- **Time Complexity**: All operations (`push`, `pop`, and `peek`) are `O(1)` as they are executed at the end of the array.
- **Space Complexity**: `O(n)` where `n` is the size of the array.

**Code**:
```java
class Stack {
    int[] stack;
    int top;

    Stack(int size) {
        stack = new int[size];
        top = -1;
    }

    void push(int value) {
        if (top == stack.length - 1) {
            System.out.println("Stack Overflow");
            return;
        }
        stack[++top] = value;
    }

    int pop() {
        if (top == -1) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return stack[top--];
    }

    int peek() {
        if (top == -1) {
            System.out.println("Stack is empty");
            return -1;
        }
        return stack[top];
    }
}
```
- **Explanation**: The stack follows the **Last In First Out (LIFO)** principle. We use the `top` index to keep track of the last pushed element.

---

### **4. Queue**

#### **Question**: How do you implement a queue using a linked list?

**Approach**:
- A queue follows the **First In First Out (FIFO)** principle. 
- For each operation (`enqueue` and `dequeue`), maintain `front` and `rear` pointers:
  - **Enqueue**: Add new nodes at the `rear`.
  - **Dequeue**: Remove nodes from the `front`.

**Logic & Intuition**:
- **Time Complexity**: `O(1)` for both `enqueue` and `dequeue`.
- **Space Complexity**: `O(n)` for `n` nodes in the queue.

**Code**:
```java
class Queue {
    class Node {
        int data;
        Node next;
        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    Node front, rear;

    void enqueue(int value) {
        Node newNode = new Node(value);
        if (rear == null) {
            front = rear = newNode;
        } else {
            rear.next = newNode;
            rear = newNode;
        }
    }

    int dequeue() {
        if (front == null) {
            System.out.println("Queue is empty");
            return -1;
        }
        int value = front.data;
        front = front.next;
        if (front == null) rear = null; // Queue becomes empty
        return value;
    }
}
```
- **Explanation**: We use two pointers to track the front and rear of the queue. This allows for efficient O(1) enqueue and dequeue operations.

---

### **5. Binary Tree**

#### **Question**: How do you perform inorder traversal of a binary tree?

**Approach**:
- **Inorder Traversal** visits the left subtree, the current node, and then the right subtree.
- Recursively traverse the left subtree, then process the current node, then recursively traverse the right subtree.

**Logic & Intuition**:
- **Time Complexity**: `O(n)` where `n` is the number of nodes in the tree.
- **Space Complexity**: `O(h)` where `h` is the height of the tree (for recursion stack).

**Code**:
```java
class TreeNode {
    int data;
    TreeNode left, right;

    TreeNode(int data) {
        this.data = data;
        this.left = this.right = null;
    }
}

void inorderTraversal(TreeNode root) {
    if (root != null) {
        inorderTraversal(root.left);
        System.out.print(root.data + " ");
        inorderTraversal(root.right);
    }
}
```
- **Explanation**

: The recursive method visits nodes in left-root-right order.

---

#### **Question**: How do you find the height of a binary tree?

**Approach**:
- The height of the tree is the longest path from the root to a leaf. This is computed by recursively finding the height of the left and right subtrees, and returning the maximum of both heights plus one.

**Logic & Intuition**:
- **Time Complexity**: `O(n)` where `n` is the number of nodes.
- **Space Complexity**: `O(h)` where `h` is the height of the tree.

**Code**:
```java
int height(TreeNode root) {
    if (root == null) return 0;
    int leftHeight = height(root.left);
    int rightHeight = height(root.right);
    return Math.max(leftHeight, rightHeight) + 1;
}
```
- **Explanation**: The function computes the height by finding the height of left and right subtrees recursively and choosing the larger one.

---

### **6. Binary Search Tree (BST)**

#### **Question**: How do you search for an element in a Binary Search Tree (BST)?

**Approach**:
- In a **Binary Search Tree (BST)**, for each node:
  - The left subtree contains values smaller than the node.
  - The right subtree contains values greater than the node.
- Start from the root:
  - If the value to be searched is smaller than the current node, move to the left subtree.
  - If it’s larger, move to the right subtree.
  - If the value matches, return true (found).
  - If the subtree is `null`, return false (not found).

**Logic & Intuition**:
- **Time Complexity**: `O(h)`, where `h` is the height of the tree. In the worst case (unbalanced tree), this could be `O(n)` where `n` is the number of nodes. In a balanced tree, it’s `O(log n)`.
- **Space Complexity**: `O(1)` for iterative solution, or `O(h)` for recursive solution due to stack space used in recursion.

**Code**:
```java
class BST {
    class Node {
        int data;
        Node left, right;

        Node(int data) {
            this.data = data;
            this.left = this.right = null;
        }
    }

    Node root;

    boolean search(Node root, int value) {
        if (root == null) return false;
        if (root.data == value) return true;
        if (value < root.data) return search(root.left, value);
        return search(root.right, value);
    }
}
```
- **Explanation**: This recursive function compares the value with the root’s data and either searches in the left or right subtree, depending on the comparison result.

---

#### **Question**: How do you insert an element into a Binary Search Tree (BST)?

**Approach**:
- Start from the root node.
- Compare the value to be inserted with the current node:
  - If it is smaller, move to the left subtree.
  - If it is larger, move to the right subtree.
- Repeat the comparison until we find an empty spot (i.e., a `null` pointer).
- Insert the node at that spot.

**Logic & Intuition**:
- **Time Complexity**: `O(h)` where `h` is the height of the tree. In a balanced tree, this is `O(log n)` and in the worst case (unbalanced tree), it can be `O(n)`.
- **Space Complexity**: `O(1)` for iterative insertion and `O(h)` for recursive insertion.

**Code**:
```java
Node insert(Node root, int value) {
    if (root == null) {
        root = new Node(value); // Insert the new node
        return root;
    }
    if (value < root.data) {
        root.left = insert(root.left, value); // Insert in left subtree
    } else {
        root.right = insert(root.right, value); // Insert in right subtree
    }
    return root;
}
```
- **Explanation**: The insertion follows the same pattern as the search algorithm but inserts the new node at the appropriate `null` position in the tree.

---

### **7. Heaps**

#### **Question**: What is a Max-Heap, and how do you insert an element into it?

**Approach**:
- A **Max-Heap** is a complete binary tree where the value of each node is greater than or equal to the values of its children.
- Insertion follows these steps:
  - Add the new element at the next available position in the tree (last level).
  - **Heapify-up**: Compare the newly inserted element with its parent and swap if the newly inserted element is greater. Repeat this process until the heap property is satisfied.

**Logic & Intuition**:
- **Time Complexity**: `O(log n)` as we need to traverse from the inserted element up to the root.
- **Space Complexity**: `O(1)` as it’s done in-place in the heap array.

**Code**:
```java
class MaxHeap {
    int[] heap;
    int size;

    MaxHeap(int capacity) {
        heap = new int[capacity];
        size = 0;
    }

    void insert(int value) {
        if (size == heap.length) return; // Overflow condition
        heap[size] = value; // Insert at the last position
        size++;
        heapifyUp(size - 1); // Ensure the heap property is maintained
    }

    void heapifyUp(int index) {
        while (index > 0 && heap[parent(index)] < heap[index]) {
            swap(index, parent(index)); // Swap with parent
            index = parent(index);
        }
    }

    int parent(int index) {
        return (index - 1) / 2;
    }

    void swap(int i, int j) {
        int temp = heap[i];
        heap[i] = heap[j];
        heap[j] = temp;
    }
}
```
- **Explanation**: Insertion into a Max-Heap places the new element at the last position, and then we perform **heapify-up** to restore the Max-Heap property.

---

#### **Question**: How do you extract the maximum element from a Max-Heap?

**Approach**:
- The root of a Max-Heap contains the maximum element.
- To extract the maximum:
  - Swap the root with the last element.
  - Remove the last element (which is now the maximum).
  - **Heapify-down** from the root to restore the heap property.

**Logic & Intuition**:
- **Time Complexity**: `O(log n)` because we need to **heapify-down** the root element to restore the heap property.
- **Space Complexity**: `O(1)` as this operation is done in-place.

**Code**:
```java
int extractMax() {
    if (size <= 0) return Integer.MIN_VALUE;
    if (size == 1) {
        size--;
        return heap[0];
    }
    // Swap root with last element
    swap(0, size - 1);
    size--;
    heapifyDown(0); // Restore the heap property
    return heap[size];
}

void heapifyDown(int index) {
    int largest = index;
    int left = 2 * index + 1;
    int right = 2 * index + 2;

    if (left < size && heap[left] > heap[largest]) largest = left;
    if (right < size && heap[right] > heap[largest]) largest = right;
    if (largest != index) {
        swap(index, largest);
        heapifyDown(largest); // Recursively heapify
    }
}
```
- **Explanation**: After extracting the maximum element, we **heapify-down** the root element to restore the heap property.

---

### **8. Hashing**

#### **Question**: How do you handle collisions in a hash table?

**Approach**:
- **Collisions** occur when two keys hash to the same index.
- Two common ways to handle collisions are:
  1. **Chaining**: Use a linked list at each table index to store multiple elements that hash to the same index.
  2. **Open Addressing**: Find the next available slot in the table for an element when a collision occurs.

**Logic & Intuition**:
- **Time Complexity**: `O(1)` for insertion, deletion, and search in ideal cases (no collisions).
- **Space Complexity**: Depends on the number of elements and the hash table size.

**Code for Chaining**:
```java
class HashTable {
    class Node {
        int key, value;
        Node next;
        Node(int key, int value) {
            this.key = key;
            this.value = value;
            this.next = null;
        }
    }

    Node[] table;

    HashTable(int size) {
        table = new Node[size];
    }

    void insert(int key, int value) {
        int index = key % table.length; // Hashing function
        Node newNode = new Node(key, value);
        if (table[index] == null) {
            table[index] = newNode;
        } else {
            newNode.next = table[index]; // Collision occurs, add at the head
            table[index] = newNode;
        }
    }

    Integer search(int key) {
        int index = key % table.length;
        Node current = table[index];
        while (current != null) {
            if (current.key == key) return current.value;
            current = current.next;
        }
        return null; // Key not found
    }
}
```
- **Explanation**: In the case of collisions, the new node is added to the front of the linked list at the hashed index.

---

### **9. Recursion**

#### **Question**: How do you calculate the factorial of a number using recursion?

**Approach**:
- The **factorial** of `n` is defined as:
  - `factorial(n) = n * factorial(n - 1)` for `n > 1`
  - `factorial(1) = 1` (Base case)
- Recursion breaks the problem into smaller subproblems.

**Logic & Intuition**:
- **Time Complexity**: `O(n)` due to the recursive calls.
- **Space Complexity**: `O(n)` because of the stack used by recursion.

**Code**

:
```java
int factorial(int n) {
    if (n == 1) return 1; // Base case
    return n * factorial(n - 1); // Recursive case
}
```
- **Explanation**: The function calls itself, reducing the value of `n` until it reaches the base case.

---

### **10. Stack**

#### **Question**: How do you implement a Stack using an array and perform push and pop operations?

**Approach**:
- A **Stack** follows the **LIFO (Last In, First Out)** principle.
  - **Push** operation: Insert an element at the top of the stack.
  - **Pop** operation: Remove the top element of the stack.
- The stack is typically implemented using an array or linked list.

**Logic & Intuition**:
- **Time Complexity**:
  - Push: `O(1)`
  - Pop: `O(1)`
- **Space Complexity**: `O(n)` where `n` is the number of elements in the stack.

**Code** (Array Implementation):
```java
class Stack {
    int[] stack;
    int top;
    int capacity;

    Stack(int capacity) {
        this.capacity = capacity;
        stack = new int[capacity];
        top = -1; // Initial position
    }

    boolean isFull() {
        return top == capacity - 1;
    }

    boolean isEmpty() {
        return top == -1;
    }

    void push(int value) {
        if (isFull()) {
            System.out.println("Stack Overflow");
            return;
        }
        stack[++top] = value; // Insert element at the top
    }

    int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return stack[top--]; // Remove the top element and return
    }

    int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return stack[top]; // Return the top element
    }
}
```

- **Explanation**: 
  - `push`: Adds an element to the stack by increasing the `top` index.
  - `pop`: Removes the top element and decrements the `top` index.
  - `peek`: Returns the top element without removing it.

---

### **11. Queue**

#### **Question**: How do you implement a Queue using an array and perform enqueue and dequeue operations?

**Approach**:
- A **Queue** follows the **FIFO (First In, First Out)** principle.
  - **Enqueue** operation: Insert an element at the end of the queue.
  - **Dequeue** operation: Remove the element from the front of the queue.
- The queue can be implemented using an array or a linked list.

**Logic & Intuition**:
- **Time Complexity**:
  - Enqueue: `O(1)`
  - Dequeue: `O(1)`
- **Space Complexity**: `O(n)` where `n` is the number of elements in the queue.

**Code** (Array Implementation):
```java
class Queue {
    int[] queue;
    int front, rear, size, capacity;

    Queue(int capacity) {
        this.capacity = capacity;
        queue = new int[capacity];
        front = size = 0;
        rear = capacity - 1;
    }

    boolean isFull() {
        return size == capacity;
    }

    boolean isEmpty() {
        return size == 0;
    }

    void enqueue(int value) {
        if (isFull()) {
            System.out.println("Queue Overflow");
            return;
        }
        rear = (rear + 1) % capacity;
        queue[rear] = value;
        size++;
    }

    int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue Underflow");
            return -1;
        }
        int value = queue[front];
        front = (front + 1) % capacity;
        size--;
        return value;
    }

    int frontElement() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        return queue[front];
    }
}
```
- **Explanation**:
  - `enqueue`: Adds an element to the queue and updates the `rear` index.
  - `dequeue`: Removes an element from the front and updates the `front` index.
  - `frontElement`: Returns the element at the front of the queue.

---

### **12. Linked List**

#### **Question**: How do you insert an element in a Singly Linked List?

**Approach**:
- A **Linked List** consists of nodes where each node contains:
  - Data
  - A pointer to the next node (in case of a singly linked list).
- **Insertion** in a linked list can happen in three places:
  1. **At the beginning**.
  2. **At the end**.
  3. **At a specific position**.

**Logic & Intuition**:
- **Time Complexity**:
  - Insert at beginning: `O(1)`
  - Insert at end: `O(n)` for traversing the list
  - Insert at specific position: `O(n)` for traversal
- **Space Complexity**: `O(1)` for each inserted element.

**Code** (Insertion at Beginning):
```java
class LinkedList {
    class Node {
        int data;
        Node next;
        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    Node head;

    void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        newNode.next = head; // Point new node to the current head
        head = newNode; // Move head to new node
    }

    void printList() {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
    }
}
```
- **Explanation**:
  - `insertAtBeginning`: A new node is created, and the `next` pointer of the new node is set to the current head, and then the head is updated to the new node.

---

### **13. Tree Traversal (Depth-First Search & Breadth-First Search)**

#### **Question**: What is the difference between Depth-First Search (DFS) and Breadth-First Search (BFS)?

**Approach**:
- **Depth-First Search (DFS)**:
  - DFS explores as far as possible along each branch before backtracking.
  - Can be implemented using **recursion** or a **stack**.
  - Three types of DFS traversals: **Inorder**, **Preorder**, and **Postorder**.

- **Breadth-First Search (BFS)**:
  - BFS explores all nodes at the present depth level before moving on to nodes at the next depth level.
  - Can be implemented using a **queue**.

**Logic & Intuition**:
- **DFS** is often used for exploring paths, solving puzzles like mazes, and finding connected components.
- **BFS** is used for finding the shortest path, levels in trees, or graph traversal.

**Time Complexity** (for both):
- **DFS**: `O(V + E)` where `V` is the number of vertices (nodes) and `E` is the number of edges (connections).
- **BFS**: `O(V + E)` where `V` is the number of vertices and `E` is the number of edges.

---

### **14. Searching Algorithms**

#### **Question**: What is the difference between Binary Search and Linear Search?

**Approach**:
- **Linear Search**: 
  - Search for an element sequentially in the array. It’s simple but inefficient for large arrays.
  - Time Complexity: `O(n)`
  - Space Complexity: `O(1)`
  
- **Binary Search**:
  - Binary Search works on sorted arrays. It repeatedly divides the array into half and eliminates half of the elements.
  - Time Complexity: `O(log n)`
  - Space Complexity: `O(1)`

**Code for Binary Search**:
```java
class BinarySearch {
    int binarySearch(int[] arr, int target) {
        int left = 0, right = arr.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (arr[mid] == target) return mid;
            if (arr[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return -1; // Target not found
    }
}
```
- **Explanation**: 
  - `binarySearch`: The array is divided into two halves, and the target is compared with the middle element to determine whether to search the left or right half.

---

### **15. Sorting Algorithms**

#### **Question**: How do you implement QuickSort?

**Approach**:
- **QuickSort** is a **divide-and-conquer** algorithm.
  - Choose a **pivot** element.
  - Partition the array such that elements less than the pivot are on the left, and elements greater than the pivot are on the right.
  - Recursively apply the same logic to the left and right subarrays.

**Logic & Intuition**:
- **Time Complexity**:
  - Best and Average case: `O(n log n)`
  - Worst case: `O(n^2)` (when the pivot is the smallest or largest element)
- **Space Complexity**: `O(log n)` due to recursive stack space.

**Code**:
```java
class QuickSort {
    void quickSort(int[] arr, int low, int high) {
        if (low < high)

 {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1); // Left subarray
            quickSort(arr, pi + 1, high); // Right subarray
        }
    }

    int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1;
    }
}
```

---

### **16. Heaps**

#### **Question**: How do you implement a Min-Heap and perform insertion and deletion operations?

**Approach**:
- A **Heap** is a **binary tree** that satisfies the heap property:
  - **Min-Heap**: The key of each node is less than or equal to the keys of its children.
  - **Max-Heap**: The key of each node is greater than or equal to the keys of its children.
- **Insertion** involves adding the new element at the end and "bubbling up" to restore the heap property.
- **Deletion** involves removing the root element and replacing it with the last element, then "bubbling down" to restore the heap property.

**Logic & Intuition**:
- **Insertion**: 
  - Insert the new element at the last position.
  - Compare with the parent and move it up until the heap property is satisfied.
- **Deletion**: 
  - Remove the root (min element in a Min-Heap).
  - Replace with the last element and compare it with its children, moving it down to maintain the heap property.

**Time Complexity**:
- **Insertion**: `O(log n)`
- **Deletion**: `O(log n)`

**Space Complexity**: `O(n)` where `n` is the number of elements in the heap.

**Code** (Min-Heap):
```java
class MinHeap {
    int[] heap;
    int size;
    int capacity;

    MinHeap(int capacity) {
        this.capacity = capacity;
        heap = new int[capacity];
        size = 0;
    }

    void insert(int key) {
        if (size == capacity) {
            System.out.println("Heap Overflow");
            return;
        }
        heap[size] = key;
        size++;
        heapifyUp(size - 1);
    }

    void heapifyUp(int index) {
        int parent = (index - 1) / 2;
        while (index > 0 && heap[parent] > heap[index]) {
            // Swap parent and child
            int temp = heap[parent];
            heap[parent] = heap[index];
            heap[index] = temp;
            index = parent;
            parent = (index - 1) / 2;
        }
    }

    void deleteMin() {
        if (size <= 0) {
            System.out.println("Heap Underflow");
            return;
        }
        heap[0] = heap[size - 1];
        size--;
        heapifyDown(0);
    }

    void heapifyDown(int index) {
        int leftChild = 2 * index + 1;
        int rightChild = 2 * index + 2;
        int smallest = index;

        if (leftChild < size && heap[leftChild] < heap[smallest]) {
            smallest = leftChild;
        }

        if (rightChild < size && heap[rightChild] < heap[smallest]) {
            smallest = rightChild;
        }

        if (smallest != index) {
            // Swap with the smallest child
            int temp = heap[index];
            heap[index] = heap[smallest];
            heap[smallest] = temp;
            heapifyDown(smallest);
        }
    }
}
```

- **Explanation**:
  - `insert`: Adds a new element at the end and bubbles it up to maintain the heap property.
  - `deleteMin`: Removes the root element and replaces it with the last element, then bubbles it down.

---

### **17. Hashing**

#### **Question**: What is hashing, and how does a hash table work?

**Approach**:
- **Hashing** is a technique used to map data (keys) to a fixed-size table (hash table) for quick access.
  - A **hash function** takes a key and returns an index where the value should be stored.
  - **Collisions** occur when two keys map to the same index, which is handled by techniques like **chaining** or **open addressing**.

**Logic & Intuition**:
- **Hash Function**: Converts a key into an index using a mathematical function.
- **Collision Resolution**:
  - **Chaining**: Store multiple elements at the same index using a linked list.
  - **Open Addressing**: Find the next available slot for the key (linear probing, quadratic probing).

**Time Complexity**:
- **Average case for insertion, deletion, and search**: `O(1)`
- **Worst case for insertion, deletion, and search**: `O(n)` (if there are many collisions)

**Space Complexity**: `O(n)` where `n` is the number of elements stored in the hash table.

**Code** (Hash Table with Chaining):
```java
class HashTable {
    class Node {
        int key;
        int value;
        Node next;

        Node(int key, int value) {
            this.key = key;
            this.value = value;
            this.next = null;
        }
    }

    Node[] table;
    int size;

    HashTable(int size) {
        table = new Node[size];
        this.size = size;
    }

    int hash(int key) {
        return key % size; // Simple hash function
    }

    void insert(int key, int value) {
        int index = hash(key);
        Node newNode = new Node(key, value);
        if (table[index] == null) {
            table[index] = newNode;
        } else {
            Node current = table[index];
            while (current.next != null) {
                current = current.next;
            }
            current.next = newNode;
        }
    }

    Integer search(int key) {
        int index = hash(key);
        Node current = table[index];
        while (current != null) {
            if (current.key == key) {
                return current.value;
            }
            current = current.next;
        }
        return null; // Not found
    }

    void delete(int key) {
        int index = hash(key);
        Node current = table[index];
        Node prev = null;
        while (current != null && current.key != key) {
            prev = current;
            current = current.next;
        }
        if (current == null) {
            System.out.println("Key not found");
            return;
        }
        if (prev == null) {
            table[index] = current.next; // Delete the first node
        } else {
            prev.next = current.next; // Delete the middle or last node
        }
    }
}
```

- **Explanation**:
  - `insert`: Calculates the index using the hash function and adds the element at that index using chaining.
  - `search`: Finds the element by hashing the key and traversing the linked list at the index.
  - `delete`: Deletes an element by finding it and updating the linked list.

---

### **18. Recursion**

#### **Question**: What is recursion, and how do you solve problems using recursion?

**Approach**:
- **Recursion** is a method in which a function calls itself to solve a problem. It breaks down a problem into smaller sub-problems of the same type.
- A recursive function typically has two parts:
  1. **Base case**: The simplest case, which doesn't require further recursion.
  2. **Recursive case**: The problem is divided into smaller sub-problems, and the function calls itself on these sub-problems.

**Logic & Intuition**:
- Recursion is used in problems like:
  - Calculating factorials
  - Fibonacci numbers
  - Tree traversal (DFS)
  - Searching (binary search)

**Time Complexity**:
- Depends on the problem, but generally recursive calls can lead to an exponential time complexity.
- Optimized recursion (like memoization) can reduce the time complexity.

**Code** (Factorial using Recursion):
```java
class RecursionExample {
    int factorial(int n) {
        if (n == 0) {
            return 1; // Base case
        }
        return n * factorial(n - 1); // Recursive case
    }

    public static void main(String[] args) {
        RecursionExample obj = new RecursionExample();
        System.out.println("Factorial of 5: " + obj.factorial(5));
    }
}
```

- **Explanation**:
  - The `factorial` function calls itself with a decremented value of `n` until `n` reaches 0, at which point the base case returns `1`, unwinding the recursion.

---

### **19. Tree Traversals (DFS & BFS)**

#### **Question**: How do you perform tree traversal using DFS and BFS?

**Approach**:
- **DFS** (Depth-First Search) explores the tree deeper before moving to the next level.
  - Can be implemented using **recursion** or **stack**.
  - **Inorder**, **Preorder**, and **Postorder** are the three types of DFS.
- **BFS** (Breadth-First Search) explores the tree level by level.
  - Can be implemented using a **queue**.

---

### **20. Depth First Search (DFS) and Breadth First Search (BFS)**

#### **DFS (Depth First Search)**:
- **DFS** is a graph traversal algorithm that explores as far down a branch of the tree (or graph) as possible before backtracking.
- **Types of DFS Traversal**:
  1. **Inorder** (left, root, right)
  2. **Preorder** (root, left, right)
  3. **Postorder** (left, right, root)

- **Logic & Intuition**:
  - DFS uses a **stack** (either explicit stack or recursion which uses the call stack).
  - DFS dives deep into each branch before exploring other branches. 
  - Common use cases include pathfinding, solving puzzles (like mazes), and tree traversal.
  
**Time Complexity**: `O(V + E)` where `V` is the number of vertices and `E` is the number of edges.

**Space Complexity**: `O(V)` for the stack used in recursion or an explicit stack.

**Code** (DFS Preorder Traversal):
```java
class TreeNode {
    int value;
    TreeNode left, right;
    TreeNode(int item) {
        value = item;
        left = right = null;
    }
}

class DFSExample {
    // Preorder DFS traversal
    void preorderTraversal(TreeNode root) {
        if (root == null) {
            return;
        }
        System.out.print(root.value + " ");
        preorderTraversal(root.left);
        preorderTraversal(root.right);
    }
    
    public static void main(String[] args) {
        DFSExample tree = new DFSExample();
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);

        System.out.print("Preorder Traversal: ");
        tree.preorderTraversal(root);
    }
}
```

- **Explanation**:
  - `preorderTraversal`: The function starts with the root, visits the left child, and then the right child recursively. This is the **preorder** traversal method of DFS.
  
#### **BFS (Breadth First Search)**:
- **BFS** is another graph traversal algorithm that explores all the nodes at the present depth level before moving on to the nodes at the next depth level.
- **Logic & Intuition**:
  - BFS uses a **queue**.
  - It explores all neighbors of a node first before moving to the next level of nodes.
  - BFS is often used to find the shortest path in unweighted graphs, or to traverse all levels in trees.

**Time Complexity**: `O(V + E)` where `V` is the number of vertices and `E` is the number of edges.

**Space Complexity**: `O(V)` for the queue used during traversal.

**Code** (BFS Traversal):
```java
import java.util.*;

class BFSExample {
    // BFS traversal
    void bfs(TreeNode root) {
        if (root == null) return;
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root);
        
        while (!queue.isEmpty()) {
            TreeNode node = queue.poll();
            System.out.print(node.value + " ");
            
            if (node.left != null) queue.add(node.left);
            if (node.right != null) queue.add(node.right);
        }
    }

    public static void main(String[] args) {
        BFSExample tree = new BFSExample();
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);

        System.out.print("BFS Traversal: ");
        tree.bfs(root);
    }
}
```

- **Explanation**:
  - `bfs`: The function starts by visiting the root, then adds its children to the queue. It continues processing nodes level by level.

---

### **21. Searching Algorithms**

#### **Linear Search**:
- **Linear Search** is a simple searching algorithm that checks every element in a list sequentially until the target element is found or the entire list has been searched.

**Time Complexity**: `O(n)` where `n` is the number of elements.

**Space Complexity**: `O(1)`.

**Code** (Linear Search):
```java
class LinearSearch {
    int search(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i; // Target found at index i
            }
        }
        return -1; // Target not found
    }

    public static void main(String[] args) {
        LinearSearch obj = new LinearSearch();
        int[] arr = {1, 2, 3, 4, 5};
        int target = 3;
        System.out.println("Element found at index: " + obj.search(arr, target));
    }
}
```

#### **Binary Search**:
- **Binary Search** works on **sorted** arrays. It repeatedly divides the search interval in half. 
  - If the value of the search key is less than the item in the middle, the search continues on the left half, otherwise it continues on the right half.
  
**Time Complexity**: `O(log n)` where `n` is the number of elements.

**Space Complexity**: `O(1)` (Iterative), `O(log n)` (Recursive due to recursion stack).

**Code** (Binary Search):
```java
class BinarySearch {
    int search(int[] arr, int target) {
        int low = 0, high = arr.length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            
            if (arr[mid] == target) {
                return mid; // Target found at index mid
            }
            if (arr[mid] < target) {
                low = mid + 1; // Search the right half
            } else {
                high = mid - 1; // Search the left half
            }
        }
        return -1; // Target not found
    }

    public static void main(String[] args) {
        BinarySearch obj = new BinarySearch();
        int[] arr = {1, 2, 3, 4, 5, 6, 7};
        int target = 4;
        System.out.println("Element found at index: " + obj.search(arr, target));
    }
}
```

- **Explanation**:
  - The `search` function divides the array into halves and searches for the target in the correct half based on whether the target is greater than or less than the mid element.

---

### **22. Sorting Algorithms**

#### **Bubble Sort**:
- **Bubble Sort** is a simple sorting algorithm that repeatedly steps through the list, compares adjacent items, and swaps them if they are in the wrong order.
  - This process is repeated until the list is sorted.

**Time Complexity**: `O(n^2)` in the worst case, `O(n)` if the list is already sorted.

**Space Complexity**: `O(1)`.

**Code** (Bubble Sort):
```java
class BubbleSort {
    void sort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap elements
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        BubbleSort obj = new BubbleSort();
        int[] arr = {5, 1, 4, 2, 8};
        obj.sort(arr);
        System.out.println("Sorted array: " + Arrays.toString(arr));
    }
}
```

- **Explanation**:
  - The `sort` function compares adjacent elements and swaps them if necessary, pushing the largest element to the end in each pass, which is where the "bubble" concept comes from.

#### **Quick Sort**:
- **Quick Sort** is a divide-and-conquer algorithm. It selects a pivot element and partitions the array around the pivot, placing the pivot in its correct position. Then, it recursively sorts the subarrays formed by partitioning the array.

**Time Complexity**: `O(n log n)` on average, `O(n^2)` in the worst case.

**Space Complexity**: `O(log n)`.

**Code** (Quick Sort):
```java
class QuickSort {
    void sort(int[] arr, int low, int high) {
        if (low < high) {
            int pivot = partition(arr, low, high);
            sort(arr, low, pivot - 1);  // Left of pivot
            sort(arr, pivot + 1, high);  // Right of pivot
        }
    }

    int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = (low - 1);
        
        for (int j = low; j <= high - 1; j++) {
           

 if (arr[j] < pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return (i + 1);
    }

    public static void main(String[] args) {
        QuickSort obj = new QuickSort();
        int[] arr = {10, 7, 8, 9, 1, 5};
        obj.sort(arr, 0, arr.length - 1);
        System.out.println("Sorted array: " + Arrays.toString(arr));
    }
}
```

- **Explanation**:
  - The `sort` function calls `partition` to divide the array around a pivot element, ensuring that elements smaller than the pivot are on the left and larger ones are on the right.

---
