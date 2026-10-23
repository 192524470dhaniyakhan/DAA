# TASK 6: FORMULATE THE RECURRENCE RELATION

## Algorithm Selected: Recursive Binary Search

### 1. Original Input Size

Let \(n\) be the number of student registration numbers in the sorted array.

### 2. Subproblem Size

Binary Search compares the target registration number with the middle element. If the target is not found, the algorithm continues searching in only one half of the array.

Therefore, the subproblem size becomes approximately \(n/2\).

### 3. Number of Recursive Calls

At each step, Binary Search makes **at most one recursive call** because it searches either the left half or the right half, not both.

### 4. Work Performed Outside the Recursive Call

Each call performs a constant amount of work:
- Calculate the middle index.
- Compare the target with the middle element.
- Decide which half to search.

Therefore, the work outside the recursive call is \(\Theta(1)\).

### 5. Recurrence Relation

The recurrence relation is:

\[
T(n)=T(n/2)+c,\quad n>1
\]

where:
- \(T(n)\) is the time required to search \(n\) elements.
- \(T(n/2)\) is the time required to search one half.
- \(c\) represents the constant work performed in each call.

### 6. Base Case

The recursion stops when the target is found or when the search interval becomes empty.

\[
T(1)=c_1
\]

An empty search interval also requires constant time.

### 7. Conclusion

The recurrence relation for Recursive Binary Search is:

\[
\boxed{T(n)=T(n/2)+\Theta(1)}
\]

with a constant-time base case. This recurrence represents the repeated division of the sorted array into halves and leads to a time complexity of \(\Theta(\log n)\).
