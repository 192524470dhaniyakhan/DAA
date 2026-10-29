
def brute_force_match(text, pattern):
    comparisons = 0
    positions = []
    n = len(text)
    m = len(pattern)

    for i in range(n - m + 1):
        j = 0

        while j < m:
            comparisons += 1

            if text[i + j] != pattern[j]:
                break

            j += 1

        if j == m:
            positions.append(i)

    return positions, comparisons


tests = [
    ("Quick Match", "hello world", "world"),
    ("Repeated Characters", "aaaaaaaaaa", "aaaab"),
    ("No Match", "computer science", "xyz")
]

for name, text, pattern in tests:
    positions, count = brute_force_match(text, pattern)

    print("\nTest:", name)
    print("Text:", text)
    print("Pattern:", pattern)
    print("Match positions:", positions)
    print("Character comparisons:", count)
