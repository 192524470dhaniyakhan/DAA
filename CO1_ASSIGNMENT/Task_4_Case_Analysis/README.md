# TASK 4 – ANALYSE BEST, AVERAGE AND WORST-CASE BEHAVIOUR

## 4.1 Linear Search

Linear Search checks registration numbers sequentially until the target is found or the list ends.

**Best Case:**

The target registration number is located at the first position. Only one comparison is required.

C_best(n) = 1

Time Complexity: Θ(1)

**Average Case:**

If the target is equally likely to appear at any position in the list, the average number of comparisons is:

C_avg(n) = (1 + 2 + 3 + ... + n) / n

C_avg(n) = n(n + 1) / 2n

C_avg(n) = (n + 1) / 2

Therefore, the average time complexity is Θ(n).

**Worst Case:**

The target is located at the last position or is absent from the list. The algorithm may perform n comparisons.

C_worst(n) = n

Time Complexity: Θ(n)

## 4.2 Recursive Binary Search

Binary Search repeatedly divides a sorted list into two halves.

**Best Case:**

The target registration number is the middle element of the list. Only one comparison is required.

C_best(n) = 1

Time Complexity: Θ(1)

**Average Case:**

The search interval is approximately halved at every recursive call. The number of comparisons grows logarithmically with the number of elements.

C_avg(n) = Θ(log₂ n)

Time Complexity: Θ(log n)

**Worst Case:**

The target is absent or is found only after repeated divisions of the search interval. The algorithm performs approximately log₂(n) comparisons.

C_worst(n) = ⌊log₂ n⌋ + 1

Time Complexity: Θ(log n)

**Note:** Binary Search requires the registration numbers to be sorted before searching.

## 4.3 Hash Table Search

Hash Table Search calculates the target's hash location and examines the corresponding entry. Its performance depends on the hash function and collision-resolution method.

**Best Case:**

The target is found immediately at the calculated location without collisions.

Number of operations: Constant

Time Complexity: Θ(1)

**Average Case:**

A suitable hash function distributes registration numbers effectively, keeping the expected number of entries examined small.

Expected Time Complexity: Θ(1)

**Worst Case:**

Many registration numbers collide, requiring the algorithm to examine several entries before finding the target or determining that it is absent.

Number of operations: Up to n

Worst-Case Time Complexity: O(n)

## 4.4 Comparison Table

| Algorithm | Best Case | Average Case | Worst Case |
|---|---|---|---|
| Linear Search | Θ(1) | Θ(n) | Θ(n) |
| Recursive Binary Search | Θ(1) | Θ(log n) | Θ(log n) |
| Hash Table Search | Θ(1) | Expected Θ(1) | O(n) |

## Conclusion

Linear Search performs well when the target is near the beginning but may examine every record in the worst case. Recursive Binary Search provides efficient logarithmic searching when the data is sorted. Hash Table Search provides expected constant-time lookup under suitable hashing conditions, although collisions can increase its worst-case running time to linear. These differences help determine which algorithm is appropriate for a large university student-record database.
