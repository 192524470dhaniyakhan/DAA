# TASK 10: COMPARE THEORY WITH EXPERIMENTAL BEHAVIOUR

## 10.1 Theoretical vs Experimental Performance

The theoretical analysis predicts that Linear Search requires linear time, Recursive Binary Search requires logarithmic time, and Hash Table Search provides expected constant-time lookup.

The experimental measurements recorded in Task 9 can be used to compare these predictions.

| Algorithm | Theoretical Search Complexity | Observed Behaviour |
|---|---|---|
| Linear Search | Average/Worst: Θ(n) | Execution time increased substantially as dataset size increased. |
| Recursive Binary Search | Average/Worst: Θ(log n) | Search remained fast as the dataset grew. |
| Hash Table Search | Expected: Θ(1) | Query time remained low, with a small increase in measured time. |

## 10.2 Does Experimental Growth Agree with Theory?

**Linear Search:** The experimental results support the theoretical prediction. As the dataset grows from 1,000 to 1,000,000 records, the time required for 100 queries increases significantly because the algorithm may examine many records for each query.

**Recursive Binary Search:** The results are consistent with logarithmic search complexity. The number of decisions increases slowly because each comparison eliminates approximately half of the remaining candidates. Sorting time must be considered separately.

**Hash Table Search:** The measured results are consistent with expected constant-time lookup. However, constructing the hash table requires preprocessing time and additional memory. Poor hash distribution or excessive collisions can increase lookup time.

## 10.3 Which Algorithm Scales Better?

Hash Table Search is the strongest choice among the three for repeated exact registration-number lookups because it offers expected Θ(1) lookup time after construction.

Recursive Binary Search is also efficient when the registration numbers are sorted. Linear Search is less suitable for large datasets because its search time grows linearly.

## 10.4 Reasons for Differences Between Theory and Practice

Theoretical complexity describes how an algorithm grows with input size, while actual execution time depends on several factors:

1. **Hardware:** Processor speed and available memory affect execution time.
2. **Programming language:** Python interpreter overhead influences measured performance.
3. **Preprocessing:** Sorting or constructing a hash table requires additional time.
4. **Memory and cache:** Memory allocation and cache behaviour can affect execution speed.
5. **Timing variation:** Very short operations may be affected by timer precision and system activity.

The experimental results should therefore be interpreted as measurements from the tested environment, not guaranteed timings for every computer.

## 10.5 Conclusion

The theoretical analysis and experimental observations show that algorithm selection affects the performance of the student-record system. Linear Search becomes expensive as the dataset grows, Recursive Binary Search provides logarithmic lookup after sorting, and Hash Table Search provides expected constant-time lookup after index construction. Therefore, a hash table is suitable for repeated exact-key searches, provided its memory and maintenance requirements are managed properly.
