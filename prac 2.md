```
import numpy as np

class R:
    def __init__(s, m): s.m, s.n = m, len (m)
    def refl(s): return all (s.m[i][i] for i in range (s.n))
    def symm(s): return all (s.m[i][j]== s.m[j][i] 
        for i in range (s.n) for j in range (s.n))
    def trans(s): return all(not(s.m[i][j] and s.m[j][k]) 
        or s.m[i][k] for i in range (s.n) for j in range (s.n) 
        for k in range (s.n))
    def antisymm(s): return all (not(s.m[i][j] and s.m[j][i]) 
        or i==j for i in range (s.n) for j in range (s.n))

m = np.array(list(map(int, input("Enter matrix values: ")
        .split()))).reshape(int(input("Matrix size: ")), -1)
r = R(m)

print("Equivalence Relation" if r.refl() and r.symm() and r.trans()
      else "Partial Order Relation" if r.refl() and r.antisymm() and r.trans()
      else "Neither partial nor equivalence")
```
