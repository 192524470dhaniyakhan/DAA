
import time

def knapsack(weights, values, capacity):
    n = len(weights)
    best_value = 0
    best_weight = 0
    best_items = []
    checked = 0

    start = time.perf_counter()

    for mask in range(1 << n):
        checked += 1
        total_weight = 0
        total_value = 0
        selected = []

        for i in range(n):
            if mask & (1 << i):
                total_weight += weights[i]
                total_value += values[i]
                selected.append(i + 1)

        if total_weight <= capacity and total_value > best_value:
            best_value = total_value
            best_weight = total_weight
            best_items = selected

    elapsed = time.perf_counter() - start

    return best_items, best_weight, best_value, checked, elapsed


# Small example
weights = [2, 3, 4, 5]
values = [6, 8, 9, 10]
capacity = 7

items, weight, value, checked, elapsed = knapsack(
    weights, values, capacity
)

print("Small Example")
print("Selected items:", items)
print("Total weight:", weight)
print("Maximum value:", value)
print("Subsets checked:", checked)
print("Execution time:", elapsed, "seconds")

# Test how the number of subsets grows
print("\nGrowth Experiment")

for n in [10, 15, 20]:
    weights = [(i % 5) + 1 for i in range(n)]
    values = [(i * 7) % 13 + 5 for i in range(n)]
    capacity = 3 * n

    result = knapsack(weights, values, capacity)

    print("Items:", n,
          "| Subsets:", result[3],
          "| Time:", result[4], "seconds")
