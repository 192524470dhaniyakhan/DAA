## A. Diagnose the Computational Bottleneck (2 Marks)

### Original Solution: Sequential Search

The original Sequential Search algorithm checks each record one by one until the required tool ID is found or the list ends.

The main computational bottleneck is the repeated comparison of tool IDs. As the number of records increases, the number of comparisons also increases.

Experimental evidence from Q2:

| Number of Records | Successful Search at Last Position | Unsuccessful Search |
|---:|---:|---:|
| 10 | 10 comparisons | 10 comparisons |
| 100 | 100 comparisons | 100 comparisons |
| 1000 | 1000 comparisons | 1000 comparisons |

The worst-case time complexity is O(n). The algorithm performs unnecessary repeated comparisons when many search requests are made on a large list.

## B. Define the Design Objective (2 Marks)

The objective is to reduce the number of operations required to locate a tool ID in a large collection of maintenance records.

The redesigned solution should:
- Reduce repeated sequential comparisons.
- Support fast tool-ID lookups.
- Handle successful and unsuccessful searches.
- Allow records to be added or updated when tools are issued or returned.

The measurable target is to reduce the lookup process from scanning up to n records to an average O(1) dictionary lookup, while accounting for index-building time and additional memory.

## C. Design the Revised Computational Strategy (4 Marks)

### Proposed Design: Dictionary-Based Tool Index

Instead of searching the complete list repeatedly, create a dictionary in which each tool ID is used as a key and its record is stored as the value.

For example:

`T-184 → Technician details`

When a search request arrives, the system directly checks the dictionary using the required tool ID.

### Revised Pseudocode

```text
START
Create an empty dictionary

FOR each tool record:
    Store the record using Tool ID as the key

INPUT the required Tool ID

IF Tool ID exists in the dictionary:
    Display the corresponding tool record
ELSE:
    Display "Tool not found"

STOP
```

### Changes and Trade-offs

- **Information exploited:** Tool IDs are unique keys that can be indexed.
- **Operations reduced:** Repeated scanning of the full list is avoided.
- **Preprocessing:** The dictionary must be created or updated when records change.
- **Additional memory:** O(n) space is needed to store the index.
- **Trade-off:** Dictionary lookup is average O(1), but worst-case lookup can be O(n). Record updates must keep the index accurate.

## D. Predict Before Implementing (1 Mark)

Before testing, I predict that the dictionary-based design will require fewer lookup operations than Sequential Search for large datasets, especially when the target is near the end or is absent.

The expected improvement will be measured using lookup operations and execution time. Dictionary construction time will be considered separately from lookup time.

## E. Implement and Validate the Redesign (2 Marks)

The redesigned prototype compares Sequential Search with dictionary-based lookup using datasets of 10, 100 and 1000 records. It tests both a target at the last position and a missing tool ID.

The same datasets are used for both approaches. The experiment records sequential comparisons, dictionary lookups and execution time.

The expected operation counts are:

| Records | Sequential Search: Last Item | Dictionary Lookup Operations |
|---:|---:|---:|
| 10 | 10 comparisons | 1 lookup |
| 100 | 100 comparisons | 1 lookup |
| 1000 | 1000 comparisons | 1 lookup |

For an unsuccessful search, Sequential Search also performs n comparisons, while the dictionary performs one key-lookup operation. This is a comparison of high-level operations; it does not count the dictionary's internal hash-table operations.

Actual execution times must be collected by running the prototype.

## F. Defend the Final Design (2 Marks)

The redesigned strategy is expected to improve repeated lookups because it avoids scanning each record from the beginning. The benefit becomes more important as the number of records and search requests increases.

However, the dictionary requires extra memory and preprocessing. Its performance also depends on effective hash-table behaviour and correct index maintenance.

Sequential Search may still be preferable for very small lists, infrequent searches or situations where maintaining an additional index is unnecessary.

### Final Engineering Conclusion

The dictionary-based redesign addresses the main bottleneck identified in Sequential Search by reducing repeated record comparisons. It is a suitable option for a maintenance organisation with many facilities and frequent tool-ID requests, provided that index-building costs, memory usage and record updates are managed correctly. The final decision should be supported by the actual experimental results.
