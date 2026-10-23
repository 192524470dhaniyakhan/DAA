# TASK 9: RECORD EXPERIMENTAL PERFORMANCE

## 9.1 Objective

To measure and compare the performance of Linear Search, Recursive Binary Search, and Hash Table Search using different dataset sizes.

## 9.2 Testing Procedure

The algorithms are tested using datasets containing 1,000, 10,000, 100,000, and 1,000,000 student registration numbers.

For each dataset, 100 queries are performed:
- 50 successful searches.
- 50 unsuccessful searches.

The following measurements are recorded:
1. Preprocessing time in seconds.
2. Execution time for 100 queries.
3. Average operations per query.
4. Number of successful searches.

## 9.3 Experimental Results

The following measurements are from the existing benchmark report and must be verified by rerunning the program.

| Dataset Size | Algorithm | Preprocessing (s) | Time for 100 Queries (s) | Avg. Operations/Query |
|---:|---|---:|---:|---:|
| 1,000 | Linear Search | 0.000000 | 0.003613 | 771.46 |
| 1,000 | Binary Search | 0.000109 | 0.000141 | 8.91 |
| 1,000 | Hash Table | 0.000092 | 0.000013 | 1.00 |
| 10,000 | Linear Search | 0.000000 | 0.049877 | 7,810.86 |
| 10,000 | Binary Search | 0.002256 | 0.000342 | 12.96 |
| 10,000 | Hash Table | 0.001737 | 0.000019 | 1.00 |
| 100,000 | Linear Search | 0.000000 | 0.487827 | 73,053.10 |
| 100,000 | Binary Search | 0.021093 | 0.000264 | 15.94 |
| 100,000 | Hash Table | 0.014345 | 0.000033 | 1.00 |
| 1,000,000 | Linear Search | 0.000000 | 14.940714 | 727,962.59 |
| 1,000,000 | Binary Search | 0.478399 | 0.000581 | 19.06 |
| 1,000,000 | Hash Table | 0.368292 | 0.000092 | 1.00 |

All three algorithms found 50 out of the 100 queries, as expected, because 50 queries were successful and 50 were unsuccessful.

## 9.4 Interpretation

1. **Linear Search:** Execution time increased considerably as the dataset grew because it checks registration numbers sequentially.

2. **Recursive Binary Search:** Search time remained low because the algorithm repeatedly divides the sorted dataset into halves. Its preprocessing time includes preparing the sorted data.

3. **Hash Table Search:** It recorded the lowest query time in these measurements. However, building the hash table requires additional time and memory.

## 9.5 Conclusion

The experimental results indicate that Linear Search becomes inefficient for large datasets. Recursive Binary Search provides logarithmic search complexity after sorting, while Hash Table Search provides expected constant-time lookup after index construction. For repeated registration-number searches, a hash table is a promising solution, subject to memory and index-maintenance requirements.
