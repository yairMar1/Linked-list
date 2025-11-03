# C String List Library (StrList)

A robust, from-scratch implementation of a singly linked list library for handling strings in C. This project is designed as a reusable software component with a clean, well-documented public API, focusing on dynamic memory management, pointer manipulation, and common list-based algorithms.

> The library's public interface is defined in `StrList.h`, providing a clear separation between the library's functionality and its internal implementation.

## Core Features & Functionality

This library provides a comprehensive set of functions to create, manipulate, and manage lists of strings.

#### **Basic Operations:**
- **`StrList_alloc()`**: Creates a new, empty list on the heap.
- **`StrList_free()`**: Safely deallocates all memory used by a list and its elements, preventing memory leaks.
- **`StrList_insertLast()`**: Appends a string to the end of the list.
- **`StrList_insertAt()`**: Inserts a string at a specific index.

#### **Data Removal:**
- **`StrList_remove()`**: Removes all occurrences of a specific string from the list.
- **`StrList_removeAt()`**: Removes the element at a given index.

#### **Inspection and Utilities:**
- **`StrList_size()`**: Returns the number of elements in the list.
- **`StrList_print()`**: Prints the entire list to standard output.
- **`StrList_count()`**: Counts the number of times a given string appears in the list.

#### **Advanced Algorithms:**
- **`StrList_sort()`**: Sorts the list in lexicographical (alphabetical) order.
- **`StrList_reverse()`**: Reverses the order of the elements in the list in-place.
- **`StrList_clone()`**: Creates a deep copy of the list, allocating new memory for the entire structure and its data.

## Technical Highlights & Capabilities Demonstrated

This project showcases several critical low-level programming skills.

### 1. API Design: Separation of Interface and Implementation
The project is structured as a professional, reusable library. A clear public **interface** is defined in the header file (`StrList.h`), while the corresponding **implementation** details reside entirely in the C file (`StrList.c`).

- **Why it matters:** This fundamental design principle, known as **abstraction**, is crucial for creating modular and maintainable code. It allows any developer using the library (the "client code") to know *what* the functions do simply by reading the header file, without needing to understand the complex details of *how* they are implemented. This makes the library easy to use, test, and update without breaking the code that depends on it.

### 2. Rigorous Dynamic Memory Management
The library places a strong emphasis on correct memory handling.
- **`malloc()` / `free()`**: Every node and its associated string data are managed dynamically.
- **Leak Prevention:** Functions like `StrList_free` and `StrList_clone` show a deep understanding of memory ownership and the importance of preventing memory leaks in complex scenarios like copying nested data structures.

### 3. Complex Pointer Manipulation
Mastery of pointers is demonstrated throughout the library, especially in the advanced functions:
- **`StrList_reverse()`**: Requires careful manipulation of `next` pointers to reverse the list without allocating new nodes.
- **`StrList_removeAt()`**: Involves correctly identifying the preceding node and re-linking the list to bypass the node being deleted.

### 4. Implementation of Core Algorithms
The library goes beyond basic data storage and implements key algorithms.
- **Sorting (`StrList_sort`)**: Demonstrates the ability to implement comparison-based sorting logic for a custom data structure.
- **Deep Copying (`StrList_clone`)**: Shows how to handle the complexities of duplicating a data structure that contains dynamically allocated content, ensuring the copy is completely independent.