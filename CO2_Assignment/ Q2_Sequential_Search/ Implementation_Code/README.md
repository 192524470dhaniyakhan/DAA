
def sequential_search(items, target):
    comparisons = 0

    for i in range(len(items)):
        comparisons += 1

        if items[i] == target:
            return i, comparisons

    return -1, comparisons


datasets = {
    "Small": list(range(1, 11)),
    "Medium": list(range(1, 101)),
    "Large": list(range(1, 1001))
}

for name, tools in datasets.items():
    print("\nDataset:", name)
    print("Number of tools:", len(tools))

    # Successful search at the beginning
    pos, count = sequential_search(tools, tools[0])
    print("First element:", "Found at position", pos,
          "| Comparisons:", count)

    # Successful search at the middle
    pos, count = sequential_search(tools, tools[len(tools) // 2])
    print("Middle element:", "Found at position", pos,
          "| Comparisons:", count)

    # Successful search at the end
    pos, count = sequential_search(tools, tools[-1])
    print("Last element:", "Found at position", pos,
          "| Comparisons:", count)

    # Unsuccessful search
    pos, count = sequential_search(tools, -1)
    print("Missing element:", "Not found",
          "| Comparisons:", count)
