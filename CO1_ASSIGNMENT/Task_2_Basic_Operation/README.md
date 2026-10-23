# TASK 2 – IDENTIFY THE BASIC OPERATION

## 2.1 Linear Search

**Basic Operation:** Comparison of a student registration number with the target registration number.

**Where It Occurs:** The comparison takes place inside the loop at the statement `A[i] == target`.

**Why It Is Appropriate:** The comparison determines whether the required registration number has been found. It is the main operation repeated during the search.

**Effect of Input Size (n):** If the target is the first element, only one comparison is required. If the target is at the last position or is absent, up to n comparisons are required. Therefore, the number of comparisons increases linearly with the dataset size.

## 2.2 Recursive Binary Search

**Basic Operation:** Comparison of the target registration number with the middle element of the sorted list.

**Where It Occurs:** The comparison occurs when checking whether `A[mid] == target` and determining whether the target belongs to the left or right half.

**Why It Is Appropriate:** These comparisons determine which half of the search space is selected for the next recursive call.

**Effect of Input Size (n):** Each recursive call reduces the search space to approximately half its previous size. Therefore, the number of comparisons grows logarithmically with the dataset size.

## 2.3 Hash Table Search

**Basic Operation:** Evaluation of the hash value and examination of the corresponding hash-table entry or entries.

**Where It Occurs:** The hash function calculates the location for the target registration number. If a collision occurs, additional comparisons may be required to identify the correct record.

**Why It Is Appropriate:** Hashing determines where the target should be stored or searched. The number of additional comparisons depends on the collision-resolution method and the distribution of keys.

**Effect of Input Size (n):** With a suitable hash function and a controlled collision rate, searching takes expected constant time. If many keys collide, the number of comparisons may increase with the dataset size.

## Conclusion

The dominant operation in Linear Search is the repeated comparison of registration numbers. In Recursive Binary Search, comparisons reduce the search space by half at each step. In Hash Table Search, the hash calculation identifies the expected search location, while collisions may require additional comparisons. These operations will be counted during experimental testing to compare the efficiency of the three algorithms.
