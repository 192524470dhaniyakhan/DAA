### Test 1: Point Set with Interior Points

Input points: (0,0), (4,0), (4,4), (0,4), (2,2), (1,2).

Expected outer boundary vertices:

(0,0) → (4,0) → (4,4) → (0,4) → (0,0).

The points (2,2) and (1,2) lie inside the square and are not part of the outer boundary.

### Test 2: Irregular Point Configuration

Input points: (0,1), (2,0), (5,1), (4,4), (2,5), (2,2), (3,2).

Expected outer boundary vertices:

(0,1) → (2,0) → (5,1) → (4,4) → (2,5) → (0,1).

The points (2,2) and (3,2) lie inside the boundary.

### Observation

The algorithm identifies the outer boundary by examining candidate point pairs and checking the orientation of every remaining point. Interior points do not form valid hull edges because they cause points to lie on both sides of a candidate line.

### Complexity Analysis

- Time complexity: O(n³).
- Auxiliary space complexity: O(n²) in the worst case for storing candidate edges.

The algorithm examines O(n²) point pairs and checks up to O(n) points for each pair.

### Correctness Explanation

A valid convex hull edge is a supporting line segment with all input points on one side of its line. The orientation test determines the side on which each point lies. Therefore, a candidate pair with no points on opposite sides is accepted as a potential boundary edge. For the supplied non-collinear datasets, the accepted edges form the outer boundary.

### Conclusion

The Brute-Force Convex Hull algorithm identifies the outer boundary using geometric orientation tests. It is easy to understand but becomes computationally expensive as the number of points increases because it requires O(n³) time.
