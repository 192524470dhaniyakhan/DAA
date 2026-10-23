
n = int(input("Enter the value of n: "))

i = 1
count = 0

while i < n:
    for j in range(i):
        count += 1
    i = i * 2

print("Total audit operations:", count)
print("Time Complexity: O(n)")
print("Space Complexity: O(1)")

<img width="959" height="539" alt="image" src="https://github.com/user-attachments/assets/95faccc7-30f4-442f-ac72-0d504f79677a" /><img width="959" height="539" alt="Screenshot 2026-10-23 105220" src="https://github.com/user-attachments/assets/ed05c535-e672-4722-91e2-71d43b8ef93e" />

