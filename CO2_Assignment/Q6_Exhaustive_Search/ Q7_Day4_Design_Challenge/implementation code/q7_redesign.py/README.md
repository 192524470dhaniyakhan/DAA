
import time

def sequential_search(records, target):
    comparisons = 0
    start = time.perf_counter()

    for record in records:
        comparisons += 1
        if record == target:
            elapsed = time.perf_counter() - start
            return True, comparisons, elapsed

    elapsed = time.perf_counter() - start
    return False, comparisons, elapsed


def dictionary_search(index, target):
    start = time.perf_counter()
    found = target in index
    elapsed = time.perf_counter() - start

    return found, 1, elapsed


for n in [10, 100, 1000]:
    records = [f"T-{i:04d}" for i in range(n)]

    # Build the dictionary index
    build_start = time.perf_counter()
    index = {tool_id: tool_id for tool_id in records}
    build_time = time.perf_counter() - build_start

    targets = [
        (records[-1], "Last item"),
        ("T-MISSING", "Missing item")
    ]

    print("\nDataset size:", n)
    print("Dictionary build time:", build_time, "seconds")

    for target, case in targets:
        seq_found, seq_ops, seq_time = sequential_search(
            records, target
        )

        dict_found, dict_ops, dict_time = dictionary_search(
            index, target
        )

        print("\nCase:", case)
        print("Sequential Search - Found:", seq_found,
              "| Comparisons:", seq_ops,
              "| Time:", seq_time)

        print("Dictionary Search - Found:", dict_found,
              "| Lookup operations:", dict_ops,
              "| Time:", dict_time)
