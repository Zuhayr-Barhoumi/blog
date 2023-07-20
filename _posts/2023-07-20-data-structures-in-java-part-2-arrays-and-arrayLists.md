---
title: Data Structures in Java, Part 2 - Arrays and ArrayLists
author: Zuhayr Barhumi
date: 2023-07-20 +0100
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

In this article, our dive into the world of data structures continues. This time further exploring two fundamental structures: Arrays and ArrayLists. These data structures play a crucial role in Java programming. They allow us to efficiently store and manipulate collections of elements.  
I’ll shed light on their nuances, advantages, and implementation through practical examples.

## Understanding Arrays in Java

Arrays in Java are a fundamental data structure that allows you to store and manipulate collections of elements. Let’s take a deeper dive into arrays, exploring their nuances and various aspects:

## Declaration and Initialization:

Arrays can be declared using the array type followed by square brackets.

```java
int[] numbers;
```

They can be initialized during declaration or later using the new keyword.

```java
int[] numbers = new int[4];
```

Arrays can also be initialized with specific values using an array initializer.

```java
int[] numbers = {1, 2, 3, 4};
```

## Length and Indexing:

The length of an array can be obtained using the length property.

```java
int length = numbers.length;
```

Array indexes start from 0, so the first element is accessed with index 0, the second with index 1, and so on.

Accessing an element beyond the array’s bounds will result in an ArrayIndexOutOfBoundsException. Try to produce the error:

```java
public class ArrayVulnerabilityExample {    public static void main(String[] args) {        int[] numbers = new int[4];                for (int i = 0; i < numbers.length; i++) {            numbers[i] = i + 1;        }                int value = numbers[4];        System.out.println("The value at index 4is: " + value);    }}
```

## Iterating over Arrays:

Arrays can be traversed using a loop, such as a for loop or a foreach loop (enhanced for loop).  
The loop variable can be used as an index to access elements.

```java
for (int i = 0; i < numbers.length; i++) { … }
```

## Arrays and Objects:

- Arrays can store objects as well as primitive types.
- When storing objects, the array elements hold references to the objects, not the objects themselves.
- Modifying an object through one array reference affects references to the same object.

## Multidimensional Arrays:

Java supports multidimensional arrays, which means we can create arrays of arrays. For example, we can create and initialize a 2D array like so:

```java
int[][] matrix = new int[3][3];
```

Elements of a 2D array can be accessed using two sets of square brackets

```java
int value = matrix[1][2];
```

## Arrays and System.arraycopy():

The System.arraycopy() method can be used to efficiently copy elements between arrays. It takes as arguments: the source array, source position, destination array, destination position, and length.

## Arrays and java.util.Arrays:

The java.util.Arrays class provides various utility methods for working with arrays. It includes methods like sort(), binarySearch(), equals(), fill(), and toString().

## Practical Example of Arrays

A program that takes as input an array containing a sequence of numbers and finds the missing number.

```java
public class MissingNumberFinder {    public static int findMissingNumber(int[] nums) {        int n = nums.length + 1;         int sum = (n * (n + 1)) / 2;                 int arraySum = 0;        for (int num : nums) {            arraySum += num;        }                return sum - arraySum;    }    public static void main(String[] args) {        int[] nums = {1, 2, 4, 5, 6, 7, 8, 9, 10};        int missingNumber = findMissingNumber(nums);        System.out.println("The missing number is: " + missingNumber);    }}
```

## Limitations of Arrays:

Arrays have a fixed size which means once they’re initialized they cannot be resized. To overcome this limitation, you need to create a new array with the desired size and copy the elements if your array needs resizing.

Understanding these nuances of arrays in Java is a very efficient way to use their power for data storage, manipulation, and traversal.

## Exploring ArrayLists

ArrayList is a dynamic, resizable implementation of the List interface in Java. It provides a more flexible alternative to regular arrays, allowing you to store and manipulate collections of objects with ease.

## Declaration and Initialization:

ArrayLists are part of the Java Collections Framework and are declared as objects of the `ArrayList` class.

```java
ArrayList<String> myArrayList;
```

They can be initialized during declaration or later using the `new` keyword.

```java
ArrayList<String> names = new ArrayList<>();
```

## Dynamic Size:

Unlike regular arrays, ArrayLists can dynamically grow or shrink as elements are added or removed. This gives more flexibility and eliminates the need for manual resizing or fixed size declarations.

## Class Genericity:

ArrayLists are generic which means they can hold elements of any class or object. You can specify the type of objects the ArrayList will hold when declaring it. For example, `ArrayList<Integer>` will create an ArrayList that can only hold integer values.

## Automatic Resizing:

ArrayLists handle resizing internally. When the number of elements exceeds the current capacity, the ArrayList automatically increases its capacity by allocating more memory. This resizing process, even though efficient, may involve copying the existing elements to the new memory location, resulting in a slight performance overhead.

```java
import java.util.ArrayList;public class ArrayListExample {    public static void main(String[] args) {                ArrayList<Integer> numbers = new ArrayList<>(5);                System.out.println("Initial Size: " + numbers.size());                for (int i = 1; i <= 5; i++) {            numbers.add(i);        }                System.out.println("Current Size after adding 5 elements: " + numbers.size());                for (int i = 6; i <= 10; i++) {            numbers.add(i);        }                System.out.println("Current Size after adding 10 elements: " + numbers.size());    }}
```

## Random Access and Indexing:

Similar to arrays, ArrayLists allow random access to elements based on their index. You can retrieve elements using the `get(index)` method, which provides constant-time performance. Additionally, you can modify elements by assigning a new value to a specific index.

```java
import java.util.ArrayList;public class ArrayListRandomAccessExample {    public static void main(String[] args) {                ArrayList<Integer> numbers = new ArrayList<>();                numbers.add(10);        numbers.add(20);        numbers.add(30);        numbers.add(40);        numbers.add(50);                System.out.println("Element at index 0: " + numbers.get(0));        System.out.println("Element at index 2: " + numbers.get(2));        System.out.println("Element at index 4: " + numbers.get(4));                numbers.set(1, 25);         numbers.set(3, 45);                 System.out.println("Modified ArrayList: " + numbers);    }}
```

## Dynamic Operations:

ArrayLists offer such as adding, removing, and modifying elements. Common methods include `add(element)`, `remove(index)`, `set(index, element)`, `size()`, `contains(element)`, and more. These operations make ArrayLists versatile for various data manipulation tasks.

```java
import java.util.ArrayList;public class BookManagement {    public static void main(String[] args) {                ArrayList<String> books = new ArrayList<>();                books.add("The Great Gatsby");        books.add("To Kill a Mockingbird");        books.add("1984");        books.add("Pride and Prejudice");                System.out.println("Initial List of Books: " + books);                books.add("Harry Potter and the Sorcerer's Stone");        System.out.println("List of Books after adding a new book: " + books);                books.remove(2);         System.out.println("List of Books after removing index 2: " + books);                books.set(1, "The Catcher in the Rye");         System.out.println("List of Books after modifying index 1: " + books);                String searchBook = "To Kill a Mockingbird";        if (books.contains(searchBook)) {            System.out.println("'" + searchBook + "' is present in the list of books.");        } else {            System.out.println("'" + searchBook + "' is not present in the list of books.");        }                int numBooks = books.size();        System.out.println("Number of books in the list: " + numBooks);    }}
```

## Wrapper Class and Auto-boxing:

ArrayLists can hold primitive data types indirectly by using their corresponding wrapper classes. For example, `ArrayList<Integer>` can store a list of integers. Java automatically performs auto-boxing and auto-unboxing, converting between primitive types and their corresponding wrapper classes seamlessly.

In the following example, we use an `ArrayList` named `numbers` to store a list of integers. Since `ArrayList` can only store objects and not primitive types, we use the `Integer` wrapper class to indirectly store integers in the `numbers` ArrayList:

```java
import java.util.ArrayList;public class ArrayListExample {    public static void main(String[] args) {                ArrayList<Integer> numbers = new ArrayList<>();                numbers.add(10);        numbers.add(20);        numbers.add(30);                int firstNumber = numbers.get(0);        int secondNumber = numbers.get(1);        int thirdNumber = numbers.get(2);        System.out.println("List of Numbers: " + numbers);        System.out.println("First Number: " + firstNumber);        System.out.println("Second Number: " + secondNumber);        System.out.println("Third Number: " + thirdNumber);                int sum = firstNumber + secondNumber;        int product = secondNumber * thirdNumber;        System.out.println("Sum of First and Second Number: " + sum);        System.out.println("Product of Second and Third Number: " + product);    }}
```

## Performance Considerations:

While ArrayLists provide flexibility, there are some performance considerations. Certain operations, such as inserting or removing elements from the middle of the ArrayList, can be inefficient. They require shifting subsequent elements. In those cases, alternative data structures like LinkedList may offer better performance.

```java
import java.util.ArrayList;import java.util.LinkedList;public class PerformanceComparison {    public static void main(String[] args) {        final int ELEMENTS = 100000;                ArrayList<Integer> arrayList = new ArrayList<>();        long startTime = System.currentTimeMillis();        for (int i = 0; i < ELEMENTS; i++) {            arrayList.add(i);        }        arrayList.add(ELEMENTS / 2, -1);        long endTime = System.currentTimeMillis();        long arrayListTime = endTime - startTime;                LinkedList<Integer> linkedList = new LinkedList<>();        startTime = System.currentTimeMillis();        for (int i = 0; i < ELEMENTS; i++) {            linkedList.add(i);        }        linkedList.add(ELEMENTS / 2, -1);        endTime = System.currentTimeMillis();        long linkedListTime = endTime - startTime;        System.out.println("Time taken by ArrayList (ms): " + arrayListTime);        System.out.println("Time taken by LinkedList (ms): " + linkedListTime);    }}
```

## Iteration and Enhanced For-loop:

ArrayLists support iteration using traditional for-loops or enhanced for-loops (also known as the foreach loop). You can easily traverse the elements and perform operations on them using these iteration techniques.

## Null Elements and Duplicate Values:

ArrayLists allow null elements and can contain duplicate values. You can store multiple occurrences of the same object in the ArrayList, maintaining the insertion order.

```java
import java.util.ArrayList;public class BlogPost {    private int postId;    private String title;    private String content;    private ArrayList<String> comments;    public BlogPost(int postId, String title, String content) {        this.postId = postId;        this.title = title;        this.content = content;        this.comments = new ArrayList<>();    }    public void addComment(String comment) {        comments.add(comment);    }    public ArrayList<String> getComments() {        return comments;    }    public static void main(String[] args) {                BlogPost blogPost = new BlogPost(1, "Introduction to Java", "Java is a popular programming language.");                blogPost.addComment("Great article!");        blogPost.addComment("I learned a lot from this.");        blogPost.addComment(null);         blogPost.addComment("Great article!");         blogPost.addComment("Thanks for sharing.");                ArrayList<String> comments = blogPost.getComments();        System.out.println("Comments on the blog post:");        for (String comment : comments) {            if (comment == null) {                System.out.println("No comment provided.");            } else {                System.out.println("- " + comment);            }        }    }}
```

## Thread Safety:

By default, ArrayLists are not thread-safe, meaning they are not designed for concurrent access from multiple threads. If you require thread-safe operations, you can use the `synchronizedList()` method from the `Collections` class to create a synchronized (thread-safe) version of the ArrayList.

```java
import java.util.ArrayList;import java.util.Collections;import java.util.List;public class ShoppingCart {    private List<String> items;    public ShoppingCart() {                items = Collections.synchronizedList(new ArrayList<>());    }    public void addItem(String item) {        items.add(item);    }    public List<String> getItems() {        return items;    }    public static void main(String[] args) {        ShoppingCart cart = new ShoppingCart();        Runnable customerTask = () -> {            for (int i = 1; i <= 5; i++) {                String item = "Item " + i;                cart.addItem(item);                System.out.println(Thread.currentThread().getName() + " added " + item);            }        };                Thread customer1 = new Thread(customerTask, "Customer 1");        Thread customer2 = new Thread(customerTask, "Customer 2");                customer1.start();        customer2.start();                try {            customer1.join();            customer2.join();        } catch (InterruptedException e) {            e.printStackTrace();        }                List<String> finalItems = cart.getItems();        System.out.println("Final Shopping Cart Items: " + finalItems);    }}
```

In this second article on Data Structures, we explored more of the essential data structures in Java, focusing on Array and ArrayList. On the one hand, arrays offer a fixed-size container for storing elements of the same type. ArrayLists, on the other hand, provide the flexibility of dynamic resizing. Understanding their characteristics enables you to make informed decisions when choosing the appropriate data structure for your Java programs.

Now that you have a solid understanding of arrays and ArrayLists in Java (by typing the code examples and practicing) you can confidently make use of these data structures to enhance the efficiency and functionality of your Java programs.
