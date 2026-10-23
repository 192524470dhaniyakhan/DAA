
n = int(input("Enter number of products: "))

products = []
for i in range(n):
    title = input("Enter product title: ")
    seller = input("Enter seller name: ")
    products.append((title, seller))

comparisons = 0
duplicates = []

for i in range(n - 1):
    for j in range(i + 1, n):
        comparisons += 1
        if products[i] == products[j]:
            duplicates.append(j)

print("Duplicate product positions:", duplicates)
print("Total comparisons:", comparisons)
print("Time Complexity: O(n^2)")
print("Auxiliary Space Complexity: O(1), excluding stored data")

<img width="959" height="539" alt="Screenshot 2026-10-23 104041" src="https://github.com/user-attachments/assets/06e9b7e3-3096-44aa-b75f-7fc84b784439" />
<img width="500" height="415" alt="Screenshot 2026-10-20 210446" src="https://github.com/user-attachments/assets/8b8e4ede-5e20-405c-a77d-9ff275f42748" />

