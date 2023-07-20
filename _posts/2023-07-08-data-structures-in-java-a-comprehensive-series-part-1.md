---
title: Data Structures in Java - A Comprehensive Series, Part 1
author: Zuhayr Barhumi
date: 2023-07-08 +0100
categories: [Software Development, Java, Programming]
tags:
  [
    java,
    data structures,
    programming concepts,
    software development,
    algorithm design,
  ]
pin: false
---

Efficiency, scalability, and maintainability are essential elements of software development. One crucial aspect that contributes to these attributes is the effective utilization of data structures. As programmers, we often find ourselves facing the daunting task of implementing features or writing programs without a clear path in sight.

In this piece, I share an overview of data structures in Java, their inner workings and practical applications. By understanding how these data structures operate and their unique advantages and drawbacks, you’ll be equipped with the knowledge to make informed decisions when it comes to organizing and manipulating data in your projects.

## Array

A fixed size collection of elements of the same type.

## **Syntax**:

```java
DataType[] arrayName = new DataType[size];
```

## **Example**:

```java
int[] numbers = new int[5];
```

**Complexity**: Access: O(1), Insertion/Deletion: O(n), Search: O(n)

**Advantages**: Efficient random access, simple syntax, memory-efficient for fixed-size collections.

**Disadvantages**: Fixed size, inefficient resizing, insertion or deletion requires shifting elements.

## **Utility**:

- **Random Access:** Arrays provide constant-time access to elements by their index, making them ideal for efficient element retrieval.
- **Sorting:** Arrays are well-suited for sorting algorithms, allowing in-place element swapping and efficient rearrangement.
- **Dynamic Programming:** Arrays are commonly used in dynamic programming to store intermediate results and optimize computations.
- **Mathematical Computations:** Arrays facilitate mathematical computations like matrix operations and numerical simulations, providing efficient element manipulation.
- **Lookup Tables:** Arrays serve as efficient lookup tables or dictionaries, allowing quick retrieval of values based on known keys or indices.
- **Buffering and Caching:** Arrays can be used as buffers or caches to store and process data efficiently.
- **Data Structures:** Arrays form the foundation for implementing other data structures like stacks, queues, and hash tables, ensuring efficient storage and retrieval.
- **Image and Signal Processing:** Arrays are essential in image and signal processing tasks, representing pixels or data points for manipulation and analysis.
- **Lookup and Search:** Sorted arrays enable efficient searching through techniques like binary search.
- **Graph Algorithms:** Arrays play a vital role in graph algorithms, representing graphs and facilitating efficient traversal and manipulation.

## Array Operations Example:

```java
public class ArrayExample {    public static void main(String[] args) {                int[] numbers = new int[5];                numbers[0] = 10;        numbers[1] = 20;        numbers[2] = 30;        numbers[3] = 40;        numbers[4] = 50;                System.out.println("Array elements:");        for (int i = 0; i < numbers.length; i++) {            System.out.println(numbers[i]);        }                numbers[2] = 35;                System.out.println("Updated element at index 2: " + numbers[2]);                int sum = 0;        for (int i = 0; i < numbers.length; i++) {            sum += numbers[i];        }        System.out.println("Sum of array elements: " + sum);                int max = numbers[0];        for (int i = 1; i < numbers.length; i++) {            if (numbers[i] > max) {                max = numbers[i];            }        }        System.out.println("Maximum value in the array: " + max);    }}
```

## ArrayList

A dynamically resizable array-based implementation of the List interface.

## **Syntax**:

```java
ArrayList<DataType> listName = new ArrayList<>();
```

## **Example**:

```java
ArrayList<String> names = new ArrayList<>();
```

**Complexity:** Access: O(1), Insertion/Deletion: O(n), Search: O(n)

**Advantages:** Dynamically resizable, efficient random access, utility methods.

**Disadvantages:** Higher memory overhead, slower insertion and deletion in the middle.

## **Utility**:

- **Storing and Manipulating a Collection:** ArrayList efficiently manages collections of objects with dynamic resizing.
- **Random Access and Indexing:** ArrayList enables efficient access and modification of elements by index.
- **Iterating Over Elements:** ArrayList facilitates easy iteration over elements in a sequential manner.
- **Implementing Stacks and Queues:** ArrayList can be used to implement stack and queue data structures.
- **Sorting and Searching:** ArrayList supports sorting and searching algorithms for efficient organization and retrieval.
- **Dynamic Data Storage:** ArrayList is well-suited for dynamically changing or growing data storage needs.
- **Maintaining Ordered Collections:** ArrayList is useful for maintaining elements in a specific order, such as priority queues or sorted lists.
- **Interacting with APIs:** ArrayList ensures compatibility and easy integration with APIs that expect or return ArrayList as a standard collection type.

## ArrayList Operations Example:

```java
import java.util.ArrayList;public class ArrayListExample {    public static void main(String[] args) {                ArrayList<Integer> numbers = new ArrayList<>();                numbers.add(10);        numbers.add(20);        numbers.add(30);        numbers.add(40);                System.out.println("Element at index 0: " + numbers.get(0));        System.out.println("Element at index 2: " + numbers.get(2));                numbers.set(1, 50);        System.out.println("Updated element at index 1: " + numbers.get(1));                numbers.remove(2);        System.out.println("ArrayList after removing element at index 2: " + numbers);                System.out.println("Size of the ArrayList: " + numbers.size());                System.out.println("Is the ArrayList empty? " + numbers.isEmpty());                System.out.println("Elements in the ArrayList:");        for (int number : numbers) {            System.out.println(number);        }                numbers.clear();        System.out.println("ArrayList after clearing: " + numbers);    }}
```

## LinkedList

A dynamically resizable array-based implementation of the List interface.

## **Syntax**:

```java
LinkedList<DataType> listName = new LinkedList<>();
```

## **Example**:

```java
LinkedList<Integer> numbers = new LinkedList<>();
```

**Complexity**: Access: O(n), Insertion/Deletion: O(1), Search: O(n)

**Advantages**: Efficient insertion and deletion at the beginning and middle, flexibility for modification.

**Disadvantages**: Inefficient random access, higher memory overhead per element.

## **Utility**:

- LinkedList excels in frequent insertion and deletion operations, especially at the beginning or middle of the list.
- It is well-suited for implementing stack and queue data structures efficiently.
- LinkedList is beneficial for iterative manipulation and easy traversal of elements during iterations.
- It naturally supports a doubly linked list implementation, allowing traversal in both forward and backward directions.
- LinkedList is useful for tasks requiring ordered insertion, as elements can be placed in their appropriate position.
- It allows for dynamic resizing, accommodating a variable number of elements without requiring contiguous memory.
- LinkedList adjusts its size based on the number of elements, making it suitable for adaptive list length.
- It can be used to implement circular lists, enabling elements to cycle through in a circular manner

## LinkedList Operations Example:

```java
import java.util.LinkedList;public class LinkedListExample {    public static void main(String[] args) {                LinkedList<String> linkedList = new LinkedList<>();                linkedList.add("Apple");        linkedList.add("Banana");        linkedList.add("Cherry");        linkedList.add("Durian");                System.out.println("LinkedList: " + linkedList);                int size = linkedList.size();        System.out.println("Size of LinkedList: " + size);                boolean isEmpty = linkedList.isEmpty();        System.out.println("Is LinkedList empty? " + isEmpty);                String firstElement = linkedList.get(0);        String lastElement = linkedList.getLast();        System.out.println("First element: " + firstElement);        System.out.println("Last element: " + lastElement);                linkedList.add(2, "Grapes");        System.out.println("LinkedList after adding at index 2: " + linkedList);                String removedElement = linkedList.remove(1);        System.out.println("Removed element: " + removedElement);        System.out.println("LinkedList after removing at index 1: " + linkedList);                boolean containsElement = linkedList.contains("Cherry");        System.out.println("Does LinkedList contain 'Cherry'? " + containsElement);                linkedList.clear();        System.out.println("LinkedList after clearing: " + linkedList);    }}
```

## Stack

A Last-In-First-Out (LIFO) data structure.

## **Syntax**:

```java
Stack<DataType> stackName = new Stack<>();
```

## **Example**:

```java
Stack<String> stack = new Stack<>();
```

**Complexity**: Push/Pop: O(1)

**Advantages**: Simple LIFO structure, supports push and pop operations.

**Disadvantages**: No random access, limited functionality compared to other data structures.

## **Utility**:

- **Expression Evaluation:** Efficiently evaluating mathematical expressions with parentheses, operators, and precedence.
- **Function Call and Execution:** Managing function calls and execution contexts in programming language implementations.
- **Compiler and Interpreter Implementation:** Storing activation records and managing program execution in compilers and interpreters.
- **Undo/Redo Operations:** Enabling the ability to revert or reapply changes in software applications.
- **Backtracking Algorithms:** Tracking visited nodes and backtracking to previous states in search algorithms.
- **Browser History:** Maintaining a history of visited web pages for backward navigation.
- **Text Editors:** Implementing undo and redo operations for text editing.
- **Memory Management:** Tracking allocated memory blocks and managing deallocation.

## Stack Operations Example:

```java
import java.util.EmptyStackException;public class Stack<T> {    private int size;    private Node<T> top;    private static class Node<T> {        private T data;        private Node<T> next;        public Node(T data) {            this.data = data;        }    }    public Stack() {        size = 0;        top = null;    }    public boolean isEmpty() {        return size == 0;    }    public int size() {        return size;    }    public void push(T element) {        Node<T> newNode = new Node<>(element);        newNode.next = top;        top = newNode;        size++;    }    public T pop() {        if (isEmpty()) {            throw new EmptyStackException();        }        T data = top.data;        top = top.next;        size--;        return data;    }    public T peek() {        if (isEmpty()) {            throw new EmptyStackException();        }        return top.data;    }    public static void main(String[] args) {        Stack<Integer> stack = new Stack<>();        stack.push(10);        stack.push(20);        stack.push(30);        System.out.println("Stack size: " + stack.size());        System.out.println("Top element: " + stack.peek());        System.out.println("Popping elements:");        while (!stack.isEmpty()) {            System.out.println(stack.pop());        }        System.out.println("Stack size: " + stack.size());    }}
```

## Queue

A First-In-First-Out (FIFO) data structure.

## **Syntax**:

```java
Queue<DataType> queueName = new LinkedList<>();
```

## **Example**:

```java
Queue<Integer> queue = new LinkedList<>();
```

**Complexity**: Enqueue/Dequeue: O(1)

**Advantages**: Efficient enqueue and dequeue operations, follows FIFO order.

**Disadvantages**: No random access, limited functionality compared to other data structures.

## **Utility**:

- **Task Scheduling:** Managing tasks or jobs in a specific order or based on priority.
- **Breadth-First Search (BFS):** Traversing or searching through a graph or tree structure in a breadth-first manner.
- **Event Handling:** Managing events or messages in an event-driven system or GUI.
- **Request Processing:** Handling incoming requests or messages in the order of their arrival.
- **Message Queuing:** Implementing reliable message queues for inter-process communication or distributed systems.
- **Print Spooling:** Queueing print jobs in a spooler to maintain order for processing.
- **Background Job Processing:** Managing a queue of background jobs or tasks for asynchronous processing.
- **CPU Task Scheduling:** Scheduling tasks or processes in a multi-tasking operating system.
- **Resource Allocation:** Managing a queue of resources for allocation to different entities or processes.
- **Buffering:** Implementing data buffering mechanisms for temporary storage in I/O or network communication.

## PriorityQueue

A queue where elements are ordered based on their priorities.

## **Syntax**:

```java
Queue<DataType> queueName = new LinkedList<>();
```

## **Example**:

```java
PriorityQueue<DataType> priorityQueueName = new PriorityQueue<>();
```

**Complexity**: Insertion/Deletion: O(log n), Access: O(1)

**Advantages**: Efficient insertion and retrieval based on priorities.

**Disadvantages**: No random access, limited functionality beyond priority-based operations.

## **Utility**:

- Task Scheduling: Efficiently managing tasks with different priorities or deadlines.
- Event-driven Simulations: Processing events based on their priority in real-time or time-dependent scenarios.
- Dijkstra’s Algorithm: Finding the shortest path between nodes in a graph by prioritizing the next node to visit.
- Huffman Coding: Constructing efficient compression codes by prioritizing elements based on frequency.
- Resource Allocation: Prioritizing entities for resource allocation, such as CPU, memory, or network bandwidth.
- Event-based Systems: Ordering events based on priority for processing or dispatching in event-driven architectures.
- Job Scheduling: Efficiently executing jobs based on their priority or deadline.
- A\* Search Algorithm: Optimal pathfinding by selecting the next node to explore based on cost and estimated cost

## TreeSet

A collection that stores unique elements in sorted order.

## **Syntax**:

```java
TreeSet<DataType> setName = new TreeSet<>();
```

## **Example:**

```java
TreeSet<Integer> set = new TreeSet<>();
```

**Complexity**: Insertion/Deletion/Access: O(log n)

**Advantages**: Elements stored in sorted order, efficient retrieval in sorted order.

**Disadvantages**: Slower insertion and deletion, limited functionality beyond sorted order.

## **Utility**:

- **Maintaining a Sorted Collection:** TreeSet ensures elements are stored in sorted order.
- **Finding Minimum or Maximum Elements:** TreeSet provides efficient access to the smallest and largest elements.
- **Implementing Sorted Iteration:** TreeSet allows for iteration over elements in a sorted order.
- **Handling Range Queries:** TreeSet supports retrieving subsets of elements based on a range of values.
- **Deduplicating and Maintaining Unique Elements:** TreeSet automatically eliminates duplicates and maintains uniqueness.
- **Implementing Interval-Based Data Structures:** TreeSet is suitable for implementing interval-based data structures.
- **Sorted Event Scheduling:** TreeSet enables scheduling events in a sorted order based on their time or priority.

## HashMap

A key-value mapping collection that uses hashing.

## Syntax:

```java
HashMap<KeyType, ValueType> mapName = new HashMap<>();
```

## Example:

```java
HashMap<String, Integer> map = new HashMap<>();
```

**Complexity**: Insertion/Deletion/Access: O(1) _average case_

**Advantages**: key-value lookup, supports efficient insertion and deletion.

**Disadvantages**: No specific ordering of key-value pairs, limited functionality beyond key-value storage.

## Utility:

1.  **Efficient Data Retrieval:** HashMap provides fast access to values based on unique identifiers, ideal for quick data retrieval.
2.  **Data Indexing:** HashMap efficiently associates values with unique keys, facilitating indexing and retrieval of large datasets.
3.  **Counting and Frequency Analysis:** HashMap is useful for counting occurrences and analyzing data frequencies efficiently.
4.  **Caching:** HashMap is commonly used for storing and retrieving computed or expensive-to-retrieve results, acting as a cache.
5.  **Efficient Lookup and Matching:** HashMap’s constant-time lookup enables efficient data matching and association based on specific criteria.
6.  **Removing Duplicates:** HashMap provides an efficient way to eliminate duplicates from a collection based on the elements’ keys.
7.  **Grouping and Partitioning:** HashMap facilitates efficient grouping and partitioning of data based on specific criteria.
8.  **Efficient Data Representation:** HashMap is widely used to represent relationships and mappings between entities, offering flexibility and efficiency.

## TreeMap

A key-value mapping collection that stores elements in sorted order.

## Syntax:

```java
TreeMap<KeyType, ValueType> mapName = new TreeMap<>();
```

## Example:

```java
TreeMap<Integer, String> map = new TreeMap<>();
```

**Complexity**: Insertion/Deletion/Access: O(log n)

**Advantages**: Key-value pairs stored in sorted order, efficient retrieval in sorted order.

**Disadvantages**: Slower insertion and deletion, limited functionality beyond sorted order.

## Utility:

- **Sorting:** TreeMap efficiently maintains elements in sorted order based on keys, making it ideal for sorting tasks.
- **Range Queries:** TreeMap’s subMap(), headMap(), and tailMap() methods provide efficient retrieval of elements within specific key ranges.
- **Key-Value Lookup:** TreeMap allows fast key-based lookup, enabling efficient retrieval of values associated with specific keys.
- **Floor and Ceiling Operations:** TreeMap’s floorKey(), ceilingKey(), floorEntry(), and ceilingEntry() methods facilitate finding closest keys based on a given key.
- **Iteration in Sorted Order:** TreeMap supports iteration over keys, values, or entries in their sorted order.
- **Deduplication:** TreeMap automatically deduplicates keys, ensuring each key exists only once.
- **Interval-based Operations:** TreeMap can be used for efficient interval-based operations or scheduling.
- **Data Visualization:** TreeMap’s sorted nature can be utilized for data visualization, such as generating sorted reports or displaying hierarchical data.

These descriptions provide an overview of each data structure, their syntax for instantiation, an example of usage, complexity, as well as their pros and cons. Remember to consider the specific requirements and characteristics of your application when choosing the most suitable data structure.
