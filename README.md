# Java Collections & Multithreading

## Overview
This repository provides a comprehensive guide and hands-on examples for understanding Java **Collections** and **Multithreading**. It covers fundamental concepts, real-world use cases, and best practices to help developers master these essential topics in Java programming.

## Table of Contents
- [Introduction](#introduction)
- [Java Collections Framework](#java-collections-framework)
  - [List](#list)
  - [Set](#set)
  - [Map](#map)
  - [Queue](#queue)
- [Multithreading in Java](#multithreading-in-java)
  - [Thread Class](#thread-class)
  - [Runnable Interface](#runnable-interface)
  - [Executor Framework](#executor-framework)
  - [Synchronization](#synchronization)
  - [Concurrency Utilities](#concurrency-utilities)
- [Installation & Usage](#installation--usage)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction
Java **Collections Framework** and **Multithreading** are crucial for building efficient and scalable applications. Collections provide reusable data structures, while multithreading enables parallel execution and resource optimization.

## Java Collections Framework
The Java Collections Framework (JCF) provides a unified architecture for handling collections efficiently. It includes interfaces and classes for various data structures.

### List
- **ArrayList** – Dynamic array implementation
- **LinkedList** – Doubly linked list implementation
- **Vector** – Synchronized dynamic array
- **Stack** – LIFO data structure

### Set
- **HashSet** – Unordered collection, no duplicates
- **LinkedHashSet** – Maintains insertion order
- **TreeSet** – Sorted set, uses Red-Black tree

### Map
- **HashMap** – Key-value storage, fast lookup
- **LinkedHashMap** – Maintains insertion order
- **TreeMap** – Sorted keys
- **ConcurrentHashMap** – Thread-safe map implementation

### Queue
- **PriorityQueue** – Implements a priority heap
- **ArrayDeque** – Double-ended queue
- **BlockingQueue** – Used in concurrent programming

## Multithreading in Java
Java’s **multithreading** capabilities enable applications to execute multiple tasks simultaneously, improving efficiency.

### Thread Class
Creating a thread by extending the `Thread` class:
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start();
    }
}
```

### Runnable Interface
Creating a thread by implementing the `Runnable` interface:
```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.start();
    }
}
```

### Executor Framework
Using `Executors` for managing thread pools:
```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class ThreadPoolExample {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(3);
        for (int i = 0; i < 5; i++) {
            executor.execute(() -> System.out.println("Task executed by " + Thread.currentThread().getName()));
        }
        executor.shutdown();
    }
}
```

### Synchronization
Synchronization ensures thread safety when multiple threads access shared resources:
```java
class SharedResource {
    synchronized void printNumbers() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
            try { Thread.sleep(500); } catch (InterruptedException e) {}
        }
    }
}
```

### Concurrency Utilities
Java provides `java.util.concurrent` package for advanced multithreading:
- `CountDownLatch`
- `CyclicBarrier`
- `Semaphore`
- `ConcurrentHashMap`
- `BlockingQueue`

## Installation & Usage
1. Clone this repository:
   ```sh
   git clone https://github.com/your-username/collections-multithreading.git
   ```
2. Navigate to the project folder:
   ```sh
   cd collections-multithreading
   ```
3. Compile and run Java files:
   ```sh
   javac src/*.java
   java src.Main
   ```

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a new branch (`feature-branch`)
3. Commit changes
4. Push to the branch and create a Pull Request

## License
This project is licensed under the MIT License.

