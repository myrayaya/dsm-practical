```
def sol_poly():
    #input coeff of the polynomial
    func = list(map(int, 
        input("Enter your function coefficients: ")
    .split()))
    #input value of variable
    num = int(input("Enter value of your variable: "))

    value = 0
    #loop through coefficients; calculate polynomial value
    for i in range(len(func)):
        value += func[i] * num ** (len(func) - 1 - i)
        #exponent decrease with each term
    
    return value

#call function and print results
print(sol_poly())

```
