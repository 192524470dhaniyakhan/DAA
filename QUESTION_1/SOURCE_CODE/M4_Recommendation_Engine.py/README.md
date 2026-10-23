
def current_design(n):
    if n <= 1:
        return 1
    return 4 * current_design(n // 2) + n


def proposed_design(n):
    if n <= 1:
        return 1
    return 2 * proposed_design(n // 2) + n


n = int(input("Enter number of products: "))

print("Current Design Operations:", current_design(n))
print("Proposed Design Operations:", proposed_design(n))
print("Current Design Complexity: Theta(n^2)")
print("Proposed Design Complexity: Theta(n log n)")
<img width="959" height="539" alt="Screenshot 2026-10-23 110501" src="https://github.com/user-attachments/assets/f94ffe20-d61a-48d4-98f4-46d5efd0248d" />
<img width="959" height="539" alt="Screenshot 2026-10-23 110452" src="https://github.com/user-attachments/assets/0b63b636-3352-4ad6-9d50-0495b174bacf" />
