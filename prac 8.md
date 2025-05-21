```
def comp_deg():
    n = int(input("enter the no. of vertices: "))
    e = int(input("enter the no. of edges: "))
    adj = [[] for _ in range(n)]
    for _ in range(e):
        u, v = map(int, input("enter edges(from to): ").split())
        adj[u].append(v)
    in_deg = [0]*n
    out_deg = [len(adj[i]) for i in range(n)]
    for i in range(n):
        for j in range (n):
            in_deg[j] += 1
    print("\nVertex\tIn\tOut")
    for i in range(n):
        print(f"{i}\t{in_deg[i]}\t{out_deg[i]}")

comp_deg()

```
