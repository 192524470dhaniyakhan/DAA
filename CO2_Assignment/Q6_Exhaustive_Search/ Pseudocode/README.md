START
Input item weights, values, and capacity
Set maximum value = 0

Generate all possible subsets of items

FOR each subset:
    Calculate total weight and total value

    IF total weight <= capacity:
        IF total value > maximum value:
            Update maximum value
            Store the selected items

Display selected items, total weight, and maximum value
STOP
