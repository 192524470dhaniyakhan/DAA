
import matplotlib.pyplot as plt


def orientation(a, b, c):
    return ((b[0] - a[0]) * (c[1] - a[1])
            - (b[1] - a[1]) * (c[0] - a[0]))


def brute_force_hull(points):
    edges = set()
    n = len(points)

    for i in range(n):
        for j in range(i + 1, n):
            positive = False
            negative = False

            for k in range(n):
                if k == i or k == j:
                    continue

                value = orientation(points[i], points[j], points[k])

                if value > 0:
                    positive = True
                elif value < 0:
                    negative = True

            if not (positive and negative):
                edges.add((points[i], points[j]))

    return sorted(edges)


tests = {
    "Test 1 - Interior Points": [
        (0, 0), (4, 0), (4, 4), (0, 4),
        (2, 2), (1, 2)
    ],
    "Test 2 - Irregular Shape": [
        (0, 1), (2, 0), (5, 1), (4, 4),
        (2, 5), (2, 2), (3, 2)
    ]
}

for name, points in tests.items():
    edges = brute_force_hull(points)

    print("\n", name)
    print("Points:", points)
    print("Hull edges:")

    for edge in edges:
        print(edge)

    # Draw the points and boundary
    plt.figure()
    x = [p[0] for p in points]
    y = [p[1] for p in points]

    plt.scatter(x, y, label="Points")

    for a, b in edges:
        plt.plot([a[0], b[0]], [a[1], b[1]], "r-")

    plt.title(name)
    plt.xlabel("X-coordinate")
    plt.ylabel("Y-coordinate")
    plt.grid(True)
    plt.legend()
    plt.show()
