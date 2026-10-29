### Experimental Results

| Dataset | List Size | Search Condition | Comparisons |
|---|---:|---|---:|
| Small | 10 | First element | 1 |
| Small | 10 | Middle element | 6 |
| Small | 10 | Last element | 10 |
| Small | 10 | Unsuccessful search | 10 |
| Medium | 100 | First element | 1 |
| Medium | 100 | Middle element | 51 |
| Medium | 100 | Last element | 100 |
| Medium | 100 | Unsuccessful search | 100 |
| Large | 1000 | First element | 1 |
| Large | 1000 | Middle element | 501 |
| Large | 1000 | Last element | 1000 |
| Large | 1000 | Unsuccessful search | 1000 |

### Observation

Sequential Search requires fewer comparisons when the target is near the beginning of the list. When the target is at the end or absent, it examines every element. Increasing the list size increases the worst-case number of comparisons linearly.

### Complexity Analysis

- Best-case time complexity: O(1)
- Average-case time complexity: O(n)
- Worst-case time complexity: O(n)
- Auxiliary space complexity: O(1)

### Engineering Recommendation

Sequential Search is suitable for small, frequently changing lists with relatively few search requests. It is simple to implement and does not require the data to be sorted.

For a large system operating across 20 maintenance facilities, the number of records and lookup requests may increase substantially. In this situation, I would consider a hash table or database index to reduce lookup time. The choice should depend on the record volume, search frequency, update requirements and memory availability.

### Conclusion

Sequential Search is a reasonable choice for small, dynamic datasets. However, for large datasets with frequent searches, an indexed lookup approach is generally more suitable.
