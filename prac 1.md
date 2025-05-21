```#program 1

from itertools import chain, combinations, product

class SET:
    def __init__(self, elements):
        self.set = set(elements)

    def is_mem(self, element):
        return element in self.set
    
    def powerset(self):
        s = list(self.set)
        return list(chain.from_iterable(combinations(s,r)
            for r in range(len(s)+1)))
    
    def is_subset(self, other_set):
        return self.set.issubset(other_set.set)
    
    def union(self, other_set):
        return self.set.union(other_set.set)
    
    def intersection(self, other_set):
        return self.set.intersection(other_set.set)
    
    def complement(self, universal_set):
        return universal_set.set - self.set
    
    def difference(self, other_set):
        return self.set - other_set.set
    
    def symm_diff(self, other_set):
        return self.set.symmetric_difference(other_set.set)
    
    def cart_prod(self, other_set):
        return list(product(self.set, other_set.set))
    
def input_set(prompt):
    elements = input(prompt).split()
    return SET(elements)

def main():
    print("create universal set: ")
    universal_set = input_set("enter universal set elements: ")

    print("create set A: ")
    A = input_set("enter elements of set A: ")

    print("create set B: ")
    B = input_set("enter elements of set B: ")

    while True: 
        print("\n---- set operations menu ----")
        print("1. check membership")
        print("2. power set of A")
        print("3. is A subset of B?")
        print("4. union of A and B")
        print("5. intersection of A and B")
        print("6. complement of A")
        print("7. A - B and B - A (set difference)")
        print("8. symmetric difference of A and B")
        print("9. cartesian product of A and B")
        print("10. Exit")

        choice = int(input("enter your choice: "))

        if choice == 1:
            x = input("enter element to check in set A: ")
            print(f"{x} is in set A: {A.is_mem(x)}")

        elif choice == 2:
            ps = A.powerset()
            print("powerset of A: ")
            for subset in ps:
                print(set(subset))

        elif choice == 3:
            print(f"set A is a subset of set B: {A.is_subset(B)}")

        elif choice == 4:
            print("union of A and B: ", A.union(B))
        
        elif choice == 5:
            print("intersection of A and B: ", A.intersection(B))
        
        elif choice == 6:
            print("complement of A (U - A): ", A.complement(universal_set))

        elif choice == 7:
            print("A - B: ", A.difference(B))
            print("B - A: ", B.difference(A))

        elif choice == 8:
            print("symmetric difference: ", A.symm_diff(B))

        elif choice == 9:
            print("cartesian product A x B: ", A.cart_prod(B))
            for pair in A.cart_prod(B):
                print(pair)

        elif choice == 10:
            print("exiting!......")

        else:
            print("invalid choice! select from 1 - 10")

    
if __name__ == "__main__":
    main()
```
