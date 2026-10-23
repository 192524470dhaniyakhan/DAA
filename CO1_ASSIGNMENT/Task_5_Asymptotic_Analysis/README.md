# TASK 5 – PERFORM ASYMPTOTIC ANALYSIS

## 5.1 Introduction

Asymptotic analysis describes how the running time of an algorithm grows as the input size increases. In this assignment, Linear Search, Recursive Binary Search, and Hash Table Search are compared using Big-O (O), Big-Omega (Ω), and Big-Theta (Θ) notations.

Let n represent the number of student registration numbers in the university database.

## 5.2 Linear Search

Linear Search examines registration numbers one by one until the target is found or the list ends.

- Best Case: Θ(1)
- Average Case: Θ(n)
- Worst Case: Θ(n)

The average and worst-case running times grow linearly with the number of records. If the dataset increases from 1,000 to 1,000,000 records, the worst-case number of comparisons increases from 1,000 to 1,000,000.

## 5.3 Recursive Binary Search

Recursive Binary Search works on sorted data and divides the search space into two halves at each step.

- Best Case: Θ(1)
- Average Case: Θ(log n)
- Worst Case: Θ(log n)

Its search time grows logarithmically. For 1,000 records, the worst case requires approximately 10 comparisons. For 1,000,000 records, it requires approximately 20 comparisons.

If sorting is required, the preprocessing cost using an efficient comparison-based sorting algorithm is Θ(n log n). If the data is already sorted, only the search cost is considered for each lookup.

## 5.4 Hash Table Search

Hash Table Search uses a hash function to locate a registration number.

- Best Case: Θ(1)
- Average Case: Expected Θ(1)
- Worst Case: O(n)

With a suitable hash function and effective collision handling, the expected search time remains constant as the dataset grows. However, many collisions may increase the worst-case time to linear.

Building a hash table generally requires expected Θ(n) time and Θ(n) additional space.

## 5.5 Comparison of Asymptotic Growth

| Algorithm | Best Case | Average Case | Worst Case |
|---|---|---|---|
| Linear Search | Θ(1) | Θ(n) | Θ(n) |
| Recursive Binary Search | Θ(1) | Θ(log n) | Θ(log n) |
| Hash Table Search | Θ(1) | Expected Θ(1) | O(n) |

Big-O (O) represents an asymptotic upper bound, Big-Omega (Ω) represents an asymptotic lower bound, and Big-Theta (Θ) represents a tight asymptotic bound.

## 5.6 Interpretation for Large Datasets

When the number of student records increases from 1,000 to 1,000,000 or more, Linear Search may require many more comparisons. Recursive Binary Search scales efficiently when the data is sorted. Hash Table Search provides expected constant-time lookup after the table is constructed.

For frequent searches, Hash Table Search can be particularly suitable because the initial construction cost can be shared across many lookups. However, memory usage, collision handling, and update requirements must also be considered.

## Conclusion

The asymptotic analysis shows that Linear Search has linear growth, Recursive Binary Search has logarithmic search growth, and Hash Table Search offers expected constant-time lookup. For large student databases, Binary Search and Hash Table Search generally scale better than Linear Search. The final recommendation must also consider preprocessing costs and the experimental results obtained in later tasks.
