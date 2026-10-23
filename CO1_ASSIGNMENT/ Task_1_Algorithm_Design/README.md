## TASK 1 – DESIGN THE ALGORITHM

### 1.1 Problem Statement

A university maintains a large database of student records, where each student is identified by a unique registration number. The objective is to design and compare three different algorithms to determine whether a given registration number exists in the database.

The algorithms selected are Linear Search, Recursive Binary Search, and Hash Table Search. These approaches are compared to identify a suitable searching strategy for datasets ranging from 1,000 to 1,000,000 or more records.

### 1.2 Algorithm 1: Linear Search

**Basic Idea:**

Linear Search examines each registration number sequentially, starting from the first element. The search stops when the target registration number is found or the list ends.

**Design Strategy:** Iterative searching.

**Pseudocode:**

```
Algorithm LinearSearch(A, target)

1. For i = 0 to length(A) - 1
2.     If A[i] == target
3.         Return i
4. Return -1
```

**Preprocessing Required:**

No preprocessing or sorting is required. The algorithm can search an unsorted list directly.

**Justification for Selection:**

Linear Search is simple to implement and works with both sorted and unsorted data. It provides a baseline for comparing the efficiency of the other searching algorithms.

### 1.3 Algorithm 2: Recursive Binary Search

**Basic Idea:**

Binary Search operates on a sorted list. It compares the target registration number with the middle element. If the target is smaller, it searches the left half; if larger, it searches the right half. The process continues recursively until the target is found or the search interval becomes empty.

**Design Strategy:** Recursive divide-and-conquer.

**Pseudocode:**

```
Algorithm BinarySearch(A, low, high, target)

1. If low > high
2.     Return -1
3. mid = floor((low + high) / 2)
4. If A[mid] == target
5.     Return mid
6. Else if target < A[mid]
7.     Return BinarySearch(A, low, mid - 1, target)
8. Else
9.     Return BinarySearch(A, mid + 1, high, target)
```

**Preprocessing Required:**

The registration numbers must be sorted before searching. If the original data is unsorted, sorting must be included in the total computational cost.

**Justification for Selection:**

Binary Search reduces the search space by approximately half at each recursive call. It is selected to investigate the efficiency of divide-and-conquer searching on large, sorted datasets.

### 1.4 Algorithm 3: Hash Table Search

**Basic Idea:**

Hash Table Search uses a hash function to calculate the storage location of a registration number. The target is searched at the corresponding location. If collisions occur, a collision-resolution method such as chaining or open addressing is used.

**Design Strategy:** Hash-based searching.

**Pseudocode:**

```
Algorithm HashTableSearch(H, target)

1. Calculate the hash value of target
2. Locate the corresponding hash-table entry
3. Search the entry using the collision-resolution method
4. If target is found
5.     Return the corresponding record
6. Otherwise
7.     Return NOT FOUND
```

**Preprocessing Required:**

A hash table must be constructed from the student registration numbers. The construction cost and additional memory required must be considered. When new records are added, the hash table must be updated.

**Justification for Selection:**

Hash Table Search is selected because it provides expected constant-time lookup under suitable hashing conditions. It is useful for a university system that performs frequent registration-number searches.

### 1.5 Comparison of the Selected Algorithms

| Feature | Linear Search | Recursive Binary Search | Hash Table Search |
|---|---|---|---|
| Main strategy | Sequential search | Divide and conquer | Hash-based lookup |
| Implementation | Iterative | Recursive | Hash function and table |
| Data requirement | Sorted or unsorted | Sorted | Hash table constructed |
| Preprocessing | Not required | Sorting if necessary | Hash-table construction |
| Expected search time | O(n) | O(log n) | O(1) |
| Main limitation | Slow for large datasets | Requires sorted data | Requires additional memory and collision handling |

### Conclusion

Three distinct searching strategies have been selected for the university student-record system. Linear Search provides a simple baseline, Recursive Binary Search demonstrates divide-and-conquer searching, and Hash Table Search supports fast expected lookup. Their mathematical complexity and experimental performance will be investigated in the following tasks.
