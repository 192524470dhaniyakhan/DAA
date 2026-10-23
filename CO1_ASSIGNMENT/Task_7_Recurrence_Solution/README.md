# TASK 7: SOLVE THE RECURRENCE RELATION

## Algorithm: Recursive Binary Search

The recurrence relation obtained in Task 6 is:

\[
T(n)=T(n/2)+c
\]

where \(c\) is the constant time required for comparisons and calculations in each recursive call.

### Method 1: Repeated Substitution

Starting with the recurrence:

\[
T(n)=T(n/2)+c
\]

Substitute \(T(n/2)\):

\[
T(n)=T(n/4)+2c
\]

Substitute again:

\[
T(n)=T(n/8)+3c
\]

After \(k\) substitutions:

\[
T(n)=T(n/2^k)+kc
\]

The recursion stops when the subproblem size becomes 1.

\[
\frac{n}{2^k}=1
\]

Therefore,

\[
n=2^k
\]

Taking logarithms on both sides:

\[
k=\log_2 n
\]

Substituting this value into the recurrence:

\[
T(n)=T(1)+c\log_2 n
\]

Since \(T(1)\) and \(c\) are constants,

\[
\boxed{T(n)=\Theta(\log n)}
\]

### Method 2: Master Theorem

The general recurrence form is:

\[
T(n)=aT(n/b)+f(n)
\]

For Binary Search:

- \(a=1\): One recursive call.
- \(b=2\): The input is divided into two halves.
- \(f(n)=\Theta(1)\): Constant work outside the recursive call.

Calculate:

\[
n^{\log_b a}=n^{\log_2 1}=n^0=1
\]

Since \(f(n)=\Theta(1)\), the Master Theorem gives:

\[
\boxed{T(n)=\Theta(\log n)}
\]

### Conclusion

Both repeated substitution and the Master Theorem show that Recursive Binary Search has a time complexity of **\(\Theta(\log n)\)**. This makes it efficient for searching large, sorted student-registration datasets.
