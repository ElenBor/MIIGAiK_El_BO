import math

def dijkstra(adj_matrix, start):
    n = len(adj_matrix)
    distances = [math.inf] * n
    distances[start] = 0
    visited = [False] * n

    for _ in range(n):
        # Выбираем необработанную вершину с минимальным расстоянием
        min_distance = math.inf
        u = -1
        for i in range(n):
            if not visited[i] and distances[i] < min_distance:
                min_distance = distances[i]
                u = i
        if u == -1:
            break

        visited[u] = True

        # Обновляем расстояния до соседей
        for v in range(n):
            if adj_matrix[u][v] > 0 and not visited[v]:
                new_dist = distances[u] + adj_matrix[u][v]
                if new_dist < distances[v]:
                    distances[v] = new_dist

    return distances

# Пример использования:
# Матрица смежности, 0 — отсутствие ребра
graph = [
    [0, 7, 9, 0, 0, 14],
    [7, 0, 10, 15, 0, 0],
    [9, 10, 0, 11, 0, 2],
    [0, 15, 11, 0, 6, 0],
    [0, 0, 0, 6, 0, 9],
    [14, 0, 2, 0, 9, 0]
]

start_vertex = 0
distances = dijkstra(graph, start_vertex)

print(f"Кратчайшие расстояния от вершины {start_vertex}:")
for i, d in enumerate(distances):
    print(f"До вершины {i}: {d}")
