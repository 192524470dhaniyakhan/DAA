# Task 11: Recommend and Defend the Final Design

## Recommended Algorithm: Hash Table Search

I recommend **Hash Table Search** as the final design for the Student Record System because it provides fast searching for large datasets.

### 1. Justification

- **Time complexity:** Hash table search has an average-case time complexity of O(1).
- **Performance:** The experimental data shows that hash table search takes less time per query than linear and binary search in the tested datasets.
- **Large datasets:** It is suitable for searching student records using unique identifiers such as registration numbers.
- **Frequent searches:** It is appropriate when many search requests are made repeatedly.
- **Daily updates:** New student records can be added to the hash table without sorting the entire dataset again.

### 2. Comparison of Algorithms

| Algorithm | Average Search Complexity | Main Limitation |
|---|---|---|
| Linear Search | O(n) | Slow for large datasets |
| Binary Search | O(log n) | Requires sorted data |
| Hash Table Search | O(1) expected | Requires extra memory and may experience collisions |

### 3. Practical Considerations

The hash table requires additional memory to store the index. Its performance also depends on the hash function, collision-handling method, and load factor. When new student records are added, the index must be updated correctly.

### 4. Final Conclusion

Based on theoretical analysis and the reported experimental comparison, **Hash Table Search is the preferred design** for a large-scale student record system that performs frequent searches by registration number. It provides expected constant-time lookup and supports daily record additions. The final implementation should be benchmarked on the target system to confirm its performance under actual workloads.
