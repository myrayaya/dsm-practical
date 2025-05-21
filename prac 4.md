```
from itertools import product

def find_sol(n, C):
    sol = []

    for combo in product(range(C+1), repeat=n):
        if sum(combo) == C:
            sol.append(combo)
            
    return sol

# Example (can be modified):
n = 3 #no. of variables
C = 5 #constant sum value

sol = find_sol(n, C)

print(f"Solutions for x1+ x2+ .....+ x{n} = {C}:")
for solution in sol:
    print(solution)
```
