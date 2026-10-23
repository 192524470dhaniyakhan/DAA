
def sequential_search(products, key):
    for i in range(len(products)):
        if products[i] == key:
            return i
    return -1


def binary_search(products, key):
    low = 0
    high = len(products) - 1

    while low <= high:
        mid = (low + high) // 2

        if products[mid] == key:
            return mid
        elif products[mid] < key:
            low = mid + 1
        else:
            high = mid - 1

    return -1


products = input("Enter product IDs in sorted order: ").split()
key = input("Enter product ID to search: ")

print("Sequential Search Position:",
      sequential_search(products, key))

print("Binary Search Position:",
      binary_search(products, key))

print("Sequential Search: O(n)")
print("Binary Search: O(log n)")

<img width="959" height="539" alt="Screenshot 2026-10-23 105908" src="https://github.com/user-attachments/assets/a1b5aeba-7a69-4501-ab8b-e0d8ed56b448" />
<img width="959" height="539" alt="Screenshot 2026-10-23 105916" src="https://github.com/user-attachments/assets/cf51f6c3-64fc-4a30-bf99-96d37f20bddb" />
