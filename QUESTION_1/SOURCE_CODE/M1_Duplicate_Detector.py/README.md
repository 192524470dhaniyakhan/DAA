
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
