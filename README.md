# Task Scheduler using Priority Queue (C++)
## 📌 Overview
This project implements a **Task Scheduler** in C++ using the **Priority Queue (Max Heap)** data structure from scratch. 

The scheduler allows users to add tasks with different priorities and ensures that the highest priority task is always executed first. It runs as a menu-driven console application where users can efficiently manage their tasks.

> **Note:** This project was built specifically to understand how priority queues and heap data structures work internally, instead of relying on built-in libraries like `std::priority_queue`.

---

## 🧠 Key Concepts Used

### 1. Priority Queue
A Priority Queue is a data structure where elements are served based on their priority instead of the order they arrive (FIFO). 
* **Rule:** Higher priority value → Executed earlier.

### 2. Binary Heap Implementation
This project implements a Max Heap using an array. 



**Properties of the heap:**
* The **Parent** node always has a greater priority than its children.
* The **Root** node always contains the highest priority task.
* Heap operations maintain this property dynamically.

**Heap Index Relations:**
* Parent(i) = `(i - 1) / 2`
* Left Child(i) = `2 * i + 1`
* Right Child(i) = `2 * i + 2`

---

## 🏗️ Project Structure
The program is built around two main classes:

### 1. Task Class
Represents a single task in the scheduler.
* **Attributes:**
  * `description`: Details about the task
  * `activity`: Category of the task
  * `priority`: Priority level (1 - 4)

**Priority Mapping:**
| Priority Level | Activity Category |
| :---: | :--- |
| **4** | Learning |
| **3** | Coding |
| **2** | Academic |
| **1** | Outdoor Activity |

*Example Output:*
```text
****************************************
Description : Study Data Structures
Activity    : Learning
****************************************
```
### 2. TaskList Class
This class manages all tasks using the custom Max Heap implementation.

**Attributes:**
* `tasks`: Dynamic array storing the tasks
* `maxTasks`: Maximum allowed tasks in the queue
* `numberOfTasks`: Current number of active tasks
* `Work`: Title of the task list

---

## ⚙️ Heap Operations Implemented

| Operation | Function Name | Time Complexity | Description |
| :--- | :--- | :---: | :--- |
| **Add Task** | `addTask()` | O(log n) | Inserts a task at the end of the heap and calls `shiftUp()` to maintain the heap property. |
| **Remove Task** | `removeTask()` | O(log n) | Removes the highest priority task (root), replaces it with the last element, and calls `shiftDown()`. |
| **Current Priority**| `currentPriority()` | O(1) | Returns the highest priority task (root of the heap) without removing it. |
| **Next Priority** | `nextPriority()` | O(1) | Returns the second highest priority task from the children of the root. |
| **Display All** | `printTasks()` | O(n log n) | Copies the heap to a temporary array, extracts tasks in priority order for printing, and restores the original heap. |

### Core Heap Functions
* **`shiftUp()`**: Used when a task is inserted. It compares the inserted node with its parent and swaps them if the child's priority is higher, ensuring the highest priority task moves toward the root.
* **`shiftDown()`**: Used when the root is removed. It compares the new root with its children and swaps it with the largest child, repeating until the heap property is satisfied.

---

## 💻 Menu Driven Interface
The program provides a simple Command Line Interface (CLI) menu:

```text
Press 1 to add New Task
Press 2 to complete highest Priority Task
Press 3 see current Priority Task
Press 4 to see next Priority Task
Press 5 to display All Pending Tasks
Press 6 Exit from program
```
## 🚀 How to Compile and Run
Make sure you have a C++ compiler (like GCC) installed on your system.

**1. Compile the code:**
```bash
g++ task_scheduler_priority_queue.cpp -o scheduler
```
## 📚 Learning Outcomes
Building this project helped in understanding:

- [x] Implementation of a Priority Queue from scratch.
- [x] Deep dive into Binary Heap data structures.
- [x] Dynamic memory allocation in C++.
- [x] Core Object-Oriented Programming (OOP) concepts.
- [x] Writing custom Heap operations (`shiftUp`, `shiftDown`, `extractMax`).
- [x] Designing interactive menu-driven console applications.

## 🔮 Possible Improvements
Future updates to this project could include:

- [ ] Graphical UI: Moving from CLI to a Qt or Web-based Interface.
- [ ] Data Persistence: Saving and loading tasks using a local database or file system.
- [ ] Deadlines: Adding task deadlines and timestamps to handle tasks with the same priority.
- [ ] Notifications: Adding system reminders for pending tasks.
- [ ] STL Benchmarking: Adding an option to use std::priority_queue to compare performance.

## 👨‍💻 Author
**Kumar Nalin Singh** — *Built as a learning project to understand Priority Queues and Heap Data Structures in C++.*
