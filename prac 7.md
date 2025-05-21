```
class Graph:
    def __init__(self, v, t):
        self.v, self.t = v, t
        self.adj = [[] for _ in range(v)]

    def add_edge(self, u, v):
        self.adj[u].append(v)
        if self.t == 1: self.adj[v].append(u)

    def is_comp(self):
        return all(len(set(neigh)) == self.v - 1 for i, neigh in enumerate(self.adj) if self.t == 1 or i not in neigh)

    def display(self):
        for i, lst in enumerate(self.adj):
            print(f"{i}: {lst}")
    
if __name__ == "__main__":
    t = int(input("graph type(1: undirected, 2: directed): "))
    v = int(input("no. of vertices: "))
    g = Graph(v, t)

    for _ in range(int(input("no. of edges: "))):
        u, v = map(int, input("enter edge(u, v): ").split())
        g.add_edge(u, v)

    print("\nAdjacency List:")
    g.display()

    print("the graph is", "completed" if g.is_comp() else "not complete")
```
