Q1 — Sorting Under Different Data Conditions 
Problem context: E-Commerce Order Processing

The fulfilment centre needs to sort customer orders according to their dispatch priority scores. We must compare Selection Sort, Bubble Sort and Insertion Sort using different input arrangements and recommend the best algorithm when 95% of orders are already sorted. This follows your assignment question exactly. DHANIYA KHAN - CO2 ASSIGNMENT.docx

Step 1: Aim
To implement and compare Selection Sort, Bubble Sort and Insertion Sort by measuring comparisons, swaps or movements, and execution time under different input conditions.
Step 2: Create the test datasets
We'll use three datasets that reveal different behaviours.
Dataset	Input	Purpose
A — Random	[5, 2, 8, 1, 4]	Tests randomly arranged data
B — Nearly sorted	[1, 2, 4, 3, 5]	Tests data that is almost sorted
C — Edge case	[1, 2, 3, 4, 5]	Tests already-sorted data

Step 3: Predictions before execution
Algorithm	Random data	Nearly sorted	Already sorted
Selection Sort	Performs a fixed number of comparisons	Same comparison count	Same comparison count
Bubble Sort	May perform many swaps	Usually fewer swaps	Can stop early if optimized
Insertion Sort	May require many shifts	Usually performs fewer shifts	Requires very little work

Prediction: Insertion Sort should perform particularly well on nearly sorted and already-sorted data. An optimized Bubble Sort can also stop early when no swaps are needed. Selection Sort performs the same number of comparisons regardless of the initial order.
