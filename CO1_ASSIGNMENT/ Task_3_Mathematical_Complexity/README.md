# TASK 3 – DERIVE THE TIME-COMPLEXITY FUNCTION MATHEMATICALLY

## 3.1 Linear Search

Let n be the total number of student registration numbers in the list.

The basic operation is the comparison between the target registration number and each list element.

In the worst case, the algorithm examines all n elements.

Number of comparisons:

C(n) = n

Let c be the constant time required for one comparison and a be the constant overhead.

The running-time function is:

T(n) = cn + a

Therefore, the time complexity is Θ(n).

**Preprocessing Cost:** No preprocessing is required.

**Overall Cost:**

T_total(n) = T_preprocessing(n) + T_search(n)

T_total(n) = 0 + Θ(n)

T_total(n) = Θ(n)

## 3.2 Recursive Binary Search

Let n be the number of elements in the sorted list.

At each recursive call, Binary Search compares the target with the middle element and continues searching in only one half of the list.

The size of the next subproblem is approximately n/2.

The number of comparisons is approximately:

C(n) = log₂(n) + 1

The running-time function is:

T(n) = T(n/2) + c

where c represents the constant work performed during each recursive call.

After k recursive divisions:

n / 2ᵏ = 1

Therefore:

2ᵏ = n

k = log₂(n)

Hence, the time complexity is Θ(log n).

**Preprocessing Cost:** If the registration numbers are unsorted, they must first be sorted. Using an efficient comparison-based sorting algorithm, the sorting cost is Θ(n log n).

**Overall Cost:**

T_total(n) = T_sort(n) + T_search(n)

T_total(n) = Θ(n log n) + Θ(log n)

T_total(n) = Θ(n log n)

If the list is already sorted, the search itself requires Θ(log n) time.

## 3.3 Hash Table Search

Let n be the number of student registration numbers stored in the hash table.

A hash function calculates the location of the target registration number. Under suitable hashing conditions, the expected number of operations required for a search is constant.

Expected search-time function:

T_search(n) = c

Therefore, the expected search complexity is Θ(1).

However, if many registration numbers collide at the same location, the algorithm may need to examine multiple entries.

Worst-case running-time function:

T_search(n) = cn + a

Therefore, the worst-case time complexity is O(n).

**Preprocessing Cost:** Building a hash table for n records generally takes expected Θ(n) time, assuming a suitable hash function and appropriate collision handling.

**Overall Cost:**

T_total(n) = T_build(n) + T_search(n)

T_total(n) = Θ(n) + Θ(1)

T_total(n) = Θ(n)

This overall cost applies when the hash table must be built from scratch. For repeated searches using the same table, each search takes expected Θ(1) time.

## 3.4 Summary of Mathematical Analysis

| Algorithm | Search Complexity | Preprocessing Cost | Overall Initial Cost |
|---|---|---|---|
| Linear Search | Θ(n) worst case | None | Θ(n) |
| Recursive Binary Search | Θ(log n) | Θ(n log n) if sorting is required | Θ(n log n) |
| Hash Table Search | Expected Θ(1); worst-case O(n) | Expected Θ(n) to build | Expected Θ(n) |

## Conclusion

The mathematical analysis shows that Linear Search has linear worst-case running time, while Recursive Binary Search has logarithmic search time when the list is already sorted. Hash Table Search provides expected constant-time lookup after construction. When preprocessing is required, its cost must be included in the overall analysis. These results will be compared with actual experimental measurements in the later tasks.
