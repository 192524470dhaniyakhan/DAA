## Step 6: Experimental Results

### Dataset 1: Random Data
Input: `[5, 2, 8, 1, 4]`

| Algorithm | Sorted Output | Comparisons | Swaps/Shifts |
|---|---|---:|---:|
| Selection Sort | [1, 2, 4, 5, 8] | 10 | 2 |
| Bubble Sort | [1, 2, 4, 5, 8] | 10 | 6 |
| Insertion Sort | [1, 2, 4, 5, 8] | 8 | 6 |

### Dataset 2: Nearly Sorted Data
Input: `[1, 2, 4, 3, 5]`

| Algorithm | Sorted Output | Comparisons | Swaps/Shifts |
|---|---|---:|---:|
| Selection Sort | [1, 2, 3, 4, 5] | 10 | 1 |
| Bubble Sort | [1, 2, 3, 4, 5] | 7 | 1 |
| Insertion Sort | [1, 2, 3, 4, 5] | 5 | 1 |

### Dataset 3: Already Sorted Data
Input: `[1, 2, 3, 4, 5]`

| Algorithm | Sorted Output | Comparisons | Swaps/Shifts |
|---|---|---:|---:|
| Selection Sort | [1, 2, 3, 4, 5] | 10 | 0 |
| Bubble Sort | [1, 2, 3, 4, 5] | 4 | 0 |
| Insertion Sort | [1, 2, 3, 4, 5] | 4 | 0 |

### Observation

Selection Sort performs the same number of comparisons for all three datasets. Bubble Sort and Insertion Sort perform fewer comparisons when the input is already sorted or nearly sorted. Insertion Sort is particularly efficient for nearly sorted data.

**Note:** Execution time depends on the computer and must be recorded from the actual program output. The tables above contain operation counts derived from the provided implementation.

### Recommendation

Insertion Sort is recommended for the e-commerce fulfilment centre because approximately 95% of existing orders are already sorted, and only small batches of new orders are added. It can efficiently insert new orders into their correct positions with relatively little movement.

### Conclusion

The experiment shows that sorting performance depends on the input arrangement. Insertion Sort is the most suitable choice for the given workload because it performs efficiently on nearly sorted data.
