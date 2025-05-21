```
def is_comp_graph(matrix):
    n = len(matrix)
    return all (matrix[i][j] == 1 for i in range(n)
        for j in range(n) if i != j)

n = int(input("Enter number of vertices: "))
print("Enter adjacency matrix rows: ")
matrix = [list(map(int, input().split())) for _ in range(n)]

print("the graph is a complete graph" if is_comp_graph(matrix)
      else "the graph is not a complete graph")


```
