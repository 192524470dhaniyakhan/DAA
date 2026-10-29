
import time

datasets = {
    "Random": [5, 2, 8, 1, 4],
    "Nearly Sorted": [1, 2, 4, 3, 5],
    "Already Sorted": [1, 2, 3, 4, 5]
}


def selection_sort(arr):
    a = arr.copy()
    comparisons = swaps = 0
    n = len(a)

    for i in range(n - 1):
        minimum = i

        for j in range(i + 1, n):
            comparisons += 1
            if a[j] < a[minimum]:
                minimum = j

        if minimum != i:
            a[i], a[minimum] = a[minimum], a[i]
            swaps += 1

    return a, comparisons, swaps


def bubble_sort(arr):
    a = arr.copy()
    comparisons = swaps = 0
    n = len(a)

    for i in range(n - 1):
        changed = False

        for j in range(n - i - 1):
            comparisons += 1

            if a[j] > a[j + 1]:
                a[j], a[j + 1] = a[j + 1], a[j]
                swaps += 1
                changed = True

        if not changed:
            break

    return a, comparisons, swaps


def insertion_sort(arr):
    a = arr.copy()
    comparisons = shifts = 0

    for i in range(1, len(a)):
        key = a[i]
        j = i - 1

        while j >= 0:
            comparisons += 1

            if a[j] > key:
                a[j + 1] = a[j]
                shifts += 1
                j -= 1
            else:
                break

        a[j + 1] = key

    return a, comparisons, shifts


algorithms = [
    ("Selection Sort", selection_sort),
    ("Bubble Sort", bubble_sort),
    ("Insertion Sort", insertion_sort)
]

for dataset_name, data in datasets.items():
    print("\nDataset:", dataset_name, data)

    for name, algorithm in algorithms:
        start = time.perf_counter()
        result, comparisons, movements = algorithm(data)
        elapsed = time.perf_counter() - start

        print(name)
        print("Sorted:", result)
        print("Comparisons:", comparisons)
        print("Swaps/Shifts:", movements)
        print("Time (seconds):", format(elapsed, ".8f"))
