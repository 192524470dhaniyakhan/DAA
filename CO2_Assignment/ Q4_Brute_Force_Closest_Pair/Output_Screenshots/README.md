### Experimental Results

| Dataset | Number of Points (n) | Unique Pairs | Distance Calculations |
|---|---:|---:|---:|
| Small | 5 | 10 | 10 |
| Medium | 20 | 190 | 190 |
| Large | 100 | 4,950 | 4,950 |

### Observation

The number of distance calculations increases quadratically as the number of points increases. When the number of points grows from 20 to 100, the number of calculations increases from 190 to 4,950.

Each unique pair is examined exactly once. The algorithm avoids duplicate comparisons by starting the inner loop at j = i + 1.

### Complexity Analysis

- Best-case time complexity: O(n²)
- Average-case time complexity: O(n²)
- Worst-case time complexity: O(n²)
- Auxiliary space complexity: O(1), excluding the input points and output pair.

### Scalability Analysis

For this experiment, an acceptable response time is defined as one second on the test computer. The measured execution times should be checked against this limit. These three small experiments alone do not establish the exact point at which the algorithm becomes impractical.

The main limitation is that every unique pair must be examined. A redesigned strategy could reduce unnecessary distance calculations by using spatial ordering or spatial partitioning.

### Conclusion

The Brute-Force Closest Pair algorithm is simple and provides the correct closest pair by examining every possible pair. However, its quadratic time complexity limits its suitability for very large numbers of drones.
