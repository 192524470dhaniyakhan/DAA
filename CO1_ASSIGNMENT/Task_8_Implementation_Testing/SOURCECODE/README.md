# TASK 8: PYTHON IMPLEMENTATION OF SEARCHING ALGORITHMS

## Aim
To implement Linear Search, Recursive Binary Search, and Hash Table Search for finding a student's registration number.

## Python Program

```python
# Linear Search
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1


# Recursive Binary Search
def binary_search(arr, target, low, high):
    if low > high:
        return -1

    mid = (low + high) // 2

    if arr[mid] == target:
        return mid
    elif target < arr[mid]:
        return binary_search(arr, target, low, mid - 1)
    else:
        return binary_search(arr, target, mid + 1, high)


# Hash Table Search
def hash_search(table, target):
    return table.get(target, -1)


# Student registration numbers
students = [101, 105, 110, 115, 120, 125, 130]

# Create a hash table for student registration numbers
hash_table = {reg_no: i for i, reg_no in enumerate(students)}

target = int(input("Enter registration number to search: "))

# Linear Search
result1 = linear_search(students, target)
print("Linear Search:", "Found at index " + str(result1)
      if result1 != -1 else "Not Found")

# Binary Search
result2 = binary_search(students, target, 0, len(students) - 1)
print("Binary Search:", "Found at index " + str(result2)
      if result2 != -1 else "Not Found")

# Hash Table Search
result3 = hash_search(hash_table, target)
print("Hash Table Search:", "Found at index " + str(result3)
      if result3 != -1 else "Not Found")
```

## Sample Input

```text
Enter registration number to search: 115
```

## Expected Output

```text
Linear Search: Found at index 3
Binary Search: Found at index 3
Hash Table Search: Found at index 3
```

## Explanation

1. **Linear Search:** Checks registration numbers one by one until the target is found.
2. **Recursive Binary Search:** Repeatedly divides the sorted list into halves to locate the target.
3. **Hash Table Search:** Uses a dictionary to find the registration number by its key.

## Time and Space Complexity

| Algorithm | Best Time | Average Time | Worst Time |
|---|---|---|---|
| Linear Search | O(1) | O(n) | O(n) |
| Recursive Binary Search | O(1) | O(log n) | O(log n) |
| Hash Table Search | O(1) | O(1) expected | O(n) |

**Note:** Binary Search requires sorted data. The hash table in this program is built before searching, so its construction time is separate from the lookup time.
