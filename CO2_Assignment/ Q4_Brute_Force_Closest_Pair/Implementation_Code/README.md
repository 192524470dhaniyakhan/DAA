
import math
import time


def closest_pair(points):
    minimum_distance = float("inf")
    closest = None
    pairs_examined = 0
    distance_calculations = 0

    for i in range(len(points)):
        for j in range(i + 1, len(points)):
            pairs_examined += 1

            x1, y1 = points[i]
            x2, y2 = points[j]

            distance = math.sqrt(
                (x2 - x1) ** 2 + (y2 - y1) ** 2
            )
            distance_calculations += 1

            if distance < minimum_distance:
                minimum_distance = distance
                closest = (points[i], points[j])

    return closest, minimum_distance, pairs_examined, distance_calculations


datasets = {
    "Small": [(0, 0), (3, 4), (1, 1), (8, 8), (2, 2)],
    "Medium": [(i, (i * i) % 17) for i in range(20)],
    "Large": [(i, (i * i) % 101) for i in range(100)]
}

for name, points in datasets.items():
    start = time.perf_counter()

    pair, distance, pairs, calculations = closest_pair(points)

    elapsed = time.perf_counter() - start

    print("\nDataset:", name)
    print("Number of points:", len(points))
    print("Closest pair:", pair)
    print("Minimum distance:", round(distance, 4))
    print("Pairs examined:", pairs)
    print("Distance calculations:", calculations)
    print("Execution time:", format(elapsed, ".8f"), "seconds")
