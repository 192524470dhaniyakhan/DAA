## Step 4: Sample Input and Output

### Sample Input

```text
Weights = [2, 3, 4, 5]
Values = [6, 8, 9, 10]
Capacity = 7
```

### Sample Output

```text
Small Example
Selected items: [2, 3]
Total weight: 7
Maximum value: 17
Subsets checked: 16
Execution time: (measured time) seconds

Growth Experiment
Items: 10 | Subsets: 1024 | Time: (measured time) seconds
Items: 15 | Subsets: 32768 | Time: (measured time) seconds
Items: 20 | Subsets: 1048576 | Time: (measured time) seconds
```

**Explanation:**

The algorithm selects items 2 and 3. Their total weight is 7 and their total value is 17. Since the total weight does not exceed the capacity, the maximum value obtained is 17. The algorithm checks all 16 possible subsets for the four items.

## Step 5: Experimental Data

| Number of Items | Number of Subsets Checked |
|---:|---:|
| 10 | 1,024 |
| 15 | 32,768 |
| 20 | 1,048,576 |

The number of subsets is calculated using \(2^n\), where \(n\) is the number of items. As the number of items increases, the number of subsets grows exponentially.

Execution times should be recorded from the actual program output because they depend on the computer used.

## Step 6: Time and Space Complexity

| Complexity | Result |
|---|---|
| Time Complexity | O(n × 2ⁿ) |
| Auxiliary Space Complexity | O(n) |
| Number of Subsets | 2ⁿ |

The time complexity is exponential because every item can either be included or excluded from a subset. The algorithm evaluates all possible combinations to find the optimal solution.

## Step 7: Observation and Conclusion

### Observation

The Exhaustive Search algorithm checks all possible subsets to find the combination with the highest value without exceeding the given capacity. For the sample input, it selects items 2 and 3, achieving a maximum value of 17 with a total weight of 7.

The number of subsets increases exponentially as the number of items increases. Therefore, the execution time also increases significantly for larger inputs.

### Recommendation

Exhaustive Search is suitable for small datasets when finding the exact optimal solution is important. For larger datasets, dynamic programming or other optimization techniques can be used to reduce computation time.

### Conclusion

The experiment demonstrates that Exhaustive Search can find the optimal solution to the 0/1 Knapsack Problem by evaluating every possible subset. However, its exponential time complexity limits its efficiency for large datasets.

## Step 8: Output Screenshot

1. Run the Python program `exhaustive_search.py`.
2. Capture the output showing the selected items, total weight, maximum value, number of subsets checked, and execution times.
3. Save the screenshot in the `Q6_Exhaustive_Search/Output_Screenshots/` folder.
4. Include the screenshot in the final assignment report.
