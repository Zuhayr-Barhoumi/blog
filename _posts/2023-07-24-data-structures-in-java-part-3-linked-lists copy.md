---
title: Data Structures in Java, Part 3 - Linked Lists
author: Zuhayr Barhumi
date: 2023-07-24 +0100
categories: [Software Development, Java, Programming]
tags:
  [
    java,
    data structures,
    programming concepts,
    software development,
    algorithm design,
  ]
pin: true
---

We have seen so far the vital importance that data structures play in organizing and managing information effectively. Even though arrays and ArrayLists are well-known for their static size and dynamic resizing capabilities, we have at our disposal a powerful alternative that offers greater flexibility and memory efficiency — the Linked List.

Through this article, I explore the significance of linked lists in Java programming. Let’s uncover their inner workings, understand the variations (singly linked and doubly linked lists), and the scenarios where linked lists shine. Grasping the essence of linked lists enhances our understanding of data structures and paves the way for more efficient programming solutions.

## Understanding LinkedLists

A LinkedList is a linear data structure, representing a dynamic collection of elements. In this sequence of elements known as “nodes”, each element points to the next in the list.

Each node contains data, the actual value of the element, and a reference to the next node. Furthermore, the Linked List data structure has two main variations: **singly linked list** and **doubly linked list:**

## 1\. Singly Linked Lists:

Each node in a singly linked list contains a reference that points to the next node in the list. The last node (the tail) contains a reference that points to null in order to signify the end of the list.

![Illustration of Linked Lists](https://miro.medium.com/v2/resize:fit:700/1*CRGZmaARVdbx2JIu1Wvqog.png)

Singly Linked List illustration

```java
class Node {
  int data;
  Node next;

  public Node(int data) {
    this.data = data;
    this.next = null;
  }
}
```

## 2\. Doubly Linked List in Java:

In Java, the `java.util.LinkedList` class is a built-in implementation of a doubly linked list. In doubly linked lists, each node holds a reference to the next as well as a reference to the previous node. This allows for efficient traversal in both directions.

![Illustration of Doubly Linked Lists](https://miro.medium.com/v2/resize:fit:700/1*3dsXDtZUyN4GiNDEXwwNTQ.png)

Doubly Linked List illustration

```java
class Node {
  int data;
  Node next;
  Node prev;

  public Node(int data) {
    this.data = data;
    this.next = null;
    this.prev = null;
  }
}
```

## Operations on Linked Lists:

## Insertion:

**Adding a node at the beginning or prepending u**pdates the new node’s `next` reference to point to the current head and update the head `prev` reference to point to the new node. Finally, the new node becomes the head. So if we were to implement a linked list ourselves it would contain a method like so:

```java
public void prepend(int data) {
  Node newNode = new Node(data);

  if (head == null) {
    head = newNode;
  } else {
    newNode.next = head;
    head.prev = newNode;
    head = newNode;
  }
}
```

![](https://miro.medium.com/v2/resize:fit:700/1*Sf72irqowy0Rz0RoudokIA.png)

Prepending to Linked List

**Adding a node at the end or appending** to a linked list requires updating the `next` reference of the current last node to point to the new node. If the list is empty, the new node becomes the head of the linked list.

```java
public void append(int data) {
  Node newNode = new Node(data);

  if (head == null) {
    head = newNode;
  } else {
    Node current = head;
    while (current.next != null) {
      current = current.next;
    }
    current.next = newNode;
  }
}
```

**Adding a node after a specific node** requires updating the new node’s `next` reference to point to the next node in the list and updating the previous node's `next` reference to point to the new node.

```java
public void addAfter(Node specificNode, int data) {
  if (specificNode == null) {
    System.out.println("Specific node cannot be null.");
    return;
  }

  Node newNode = new Node(data);
  newNode.next = specificNode.next;
  specificNode.next = newNode;
}
```

## Deletion:

**Removing the first node** involves making the head to point to the next node in the list.

**Removing the last node** involves traversing the list to find the second-to-last node and updating its `next` reference to null.

**Removing a specific** **node** involves updating the previous node’s `next` reference to skip the node to be deleted and point directly to the next node.

## Traversal:

**Iterating through the list** by starting from the head and following the `next` references until you reach null.

## Built-in LinkedList in Java:

For better or for worse, in modern languages we don’t have to write every data structure from scratch. Java provides a built-in implementation of LinkedList in the `java.util` package as `java.util.LinkedList`. It is a doubly linked list implementation which includes various methods for adding, removing, and manipulating elements similar to the ones that I have, hitherto, explained.

## Creating a LinkedList in Java:

To create a LinkedList in Java, we need to import the `java.util.LinkedList` class and then instantiate it.

```java
import java.util.LinkedList;
LinkedList<String> myList = new LinkedList<>();
```

The above example creates an empty LinkedList that will hold string values.

## Adding Elements to the LinkedList:

To add an element to the end of the list we either use the `add(element)`or`addLast(element)`method.

```java
myList.add("enjoy");
myList.addLast("data");
myList.add("strcutures");
```

After these operations, the LinkedList now contains `[“enjoy", "data", "structures"]`.

To add an element to the beginning of the list we use`addFirst(element).`

```java
myList.addFirst("I");
```

Now, the LinkedList becomes `["I",“enjoy","data", "structures"]`.

To add an element at a specific index we use the add method,`add(index, element).`

```java
myList.add(2, "using");
```

Throw it in a class and test it out:

```java
import java.util.LinkedList;

public class Test {
  public static void main(String[] args) {
    LinkedList<String> myList = new LinkedList<>();

    myList.add("enjoy");
    myList.add("data");
    myList.add("structures");

    myList.addFirst("I");
    myList.add(2, "using");

    System.out.println(myList);
  }
}
```

```
Output:
["I",“enjoy","using", "data", "structures"]
```

## Removing Elements from the LinkedList:

Just like the add method, the`remove()` method by default perfroms its operation on the last element in the list. This time it removes the last element and **returns** it so you can use the returned value or store it in variable. The`removeLast()`does the same thing:

```java
String lastElement = myList.removeLast();
```

We’ve seen the`addFirst()`method, similarly, there is`removeFirst()`which removes but also returns the first element in the list.

```java
String firstElement = myList.removeFirst();
```

To remove the first occurrence of a specific element from the list we use`remove(element):`

```java
boolean isRemoved = myList.remove(String.valueOf("value"));
```

`remove(index)`: Removes and returns the element at a given index from the list. And of course to store the returned element, we need a variable of the same type. So if it’s an integer:

```java
int removedElement = myList.remove(1);
```

## Accessing Elements in the LinkedList:

What if we don’t want to remove the element? To return the element at a given index without removing it we use `get(index):`

```java
int elementAtIndex = myList.get(1);
```

## Modifying Elements in the LinkedList:

To replace the element at a given index with a specific element, use the`set(index, element)`method:

```java
myList.set(1, "We");
```

## Checking the Size of the LinkedList:

`The size()`returns the number of elements in the list.

```java
int size = myList.size();
```

These are only some of thecommonly used operations on a LinkedList in Java. There are plenty more which you can find on documentation sites.

LinkedLists provide dynamic memory allocation and efficient insertions and deletions. Hence, the are useful for applications where elements need to be managed in a flexible and dynamic manner.

## Advantages of LinkedLists:

- **Dynamic memory allocation:** LinkedLists allow for efficient memory allocation and deallocation. In simple terms, nodes can be added or removed easily.
- **Efficient insertions and deletions:** Inserting or deleting elements in a LinkedList can be efficient. It involves updating references.
- **No need for contiguous memory:** Unlike arrays, LinkedLists do not require contiguous memory allocation.

## Disdvantages of LinkedLists:

- **Sequential access:** Whereas in arrays we have direct access to elements by index, that is not possible in LinkedLists. To find specific elements we need to traverse the nodes in a sequential manner.
- **Extra memory:** Each node in a LinkedList requires additional memory for the reference to the next. And previous node, in the case of Doubly Linked Lists.

#### When to Use LinkedLists:

**Dynamic size and frequent insertion and deletion:** In certain scenarios, we may need to frequently insert or delete elements from a list whose size needs to change dynamically during the execution of the program. Linked Lists are an ideal way to achieve that.

**Efficient Iterations:** Accessing elements by index is slower in LinkedLists compared to arrays but iterating through **all** elements is, indeed, efficient. In other words, LinkedLists are particularly useful when you need to traverse the entire list **sequentially**.

**Implementing Graphs:** LinkedLists are commonly used to represent graphs, where each node in the list represents a vertex, and the edges are stored as references to other nodes in the list.

**Memory Efficiency:** Compared to arrays or ArrayLists, LinkedLists can be more memory-efficient. They only require memory for the data and references to the next and previous node. Arrays have additional overhead for the fixed-size buffer.

#### LinkedList vs. ArrayList:

As I’ve already mentioned some of the use cases for LinkedLists you may conclude that are a more suitable choice than Arrays and ArrayLists. However, in many other cases I’d say the opposite. For example, accessing elements by index is slower in LinkedLists than in arrays. Therefore, if your use case requires frequent insertions and deletions at the either ends of the collection or **sequential access** then use LinkedLists. If your use case, otherwise, requires frequent **random** **access**, arrays or ArrayLists might be more suitable.

As with any data structure, the choice of using a LinkedList depends on the specific requirements and constraints of the problem you are trying to solve.

## Practical Code Example of LinkedList:

One real-world example of a program that makes use of the LinkedList data structure is a web browser’s history feature. When you browse the internet using a web browser like Firefox, or Edge, or Brave, the browser keeps track of the websites you visit in a history list. This history list is usually implemented using a LinkedList.

```java
import java.util.LinkedList;

class WebPage {
    String url;
    String title;

    public WebPage(String url, String title) {
        this.url = url;
        this.title = title;
    }

    public String getUrl() {
        return url;
    }

    public String getTitle() {
        return title;
    }
}

class BrowserHistory {
    private LinkedList<WebPage> historyList;

    public BrowserHistory() {
        historyList = new LinkedList<>();
    }

    public void addPage(String url, String title) {
        WebPage newPage = new WebPage(url, title);
        historyList.addFirst(newPage); // Adding new page to the beginning of the list
    }

    public void printHistory() {
        for (WebPage page : historyList) {
            System.out.println("Title: " + page.getTitle() + ", URL: " + page.getUrl());
        }
    }
}

public class Main {
    public static void main(String[] args) {
        BrowserHistory browserHistory = new BrowserHistory();

        // Simulating browsing by adding pages to the history
        browserHistory.addPage("https://www.google.com", "Google");
        browserHistory.addPage("https://www.medium.com", "Medium");
        browserHistory.addPage("https://www.example.com", "Example Website");

        // Printing the browsing history
        System.out.println("Browsing History:");
        browserHistory.printHistory();
    }
}
```

```
Browsing History:
Title: Example Website, URL: https://www.example.com
Title: Medium, URL: https://www.medium.com
Title: Google, URL: https://www.google.com
```

To conclude, Linked lists are a fundamental data structure in Java and in programming in general. Their dynamic and efficient memory management make them invaluable for handling changing collections of data. By mastering linked lists, you are set to create more sophisticated programming solutions. We continue to explore the vast realm of data structures and we have added to our arsenal another useful tool for seamlessly adding, removing, and manipulating elements. Best use of this knowledge comes through practice and leveraging these concepts in real-world projects.
