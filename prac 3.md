```
from itertools import permutations, product

s = list(map(int, input("Enter Elements: ").split()))
print("\nWith Repitition: ")
wr = list(product(s, repeat= len(s)))
print(*wr, sep="\n")

print("\n Without Repititon: ")
wor = list(permutations(s,len(s)))
print(*wor, sep="\n")

print(f"\nCount with Repitition: {len(wr)}")
print(f"\nCount without Repittion: {len(wor)}")

```
