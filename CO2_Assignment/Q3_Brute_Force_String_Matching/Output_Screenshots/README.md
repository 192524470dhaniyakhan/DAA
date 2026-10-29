### Test 1: Quick Match

Text: `hello world`

Pattern: `world`

Expected result: Match found at index 6.

Character comparisons: 5

### Test 2: Repeated Characters

Text: `aaaaaaaaaa`

Pattern: `aaaab`

Expected result: No match found.

Character comparisons: 35

### Test 3: No Match

Text: `computer science`

Pattern: `xyz`

Expected result: No match found.

Character comparisons: 14

### Observation

The number of character comparisons depends on the text and pattern, not only their lengths. Repeated characters can cause the same pattern prefix to be compared many times before a mismatch occurs. A quick match can require fewer comparisons.

### Complexity Analysis

- Best-case time complexity: O(n), when each alignment mismatches immediately.
- Average-case time complexity: O(nm).
- Worst-case time complexity: O(nm).
- Auxiliary space complexity: O(n) for storing all match positions in the worst case.

Here, n is the text length and m is the pattern length.

### Conclusion

Brute-Force String Matching is simple to implement, but repeated comparisons can increase computational effort. For large cybersecurity logs, a more efficient string-matching strategy may be useful.
