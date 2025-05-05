import math
def f(x):
    return x**2 - math.cos(x)
def bisection_method(a, b, epsilon=1e-6, max_iter=100):
    if f(a) * f(b) > 0:
        print("Verilən intervalda kök yoxdur.")
        return None
    iter_count = 0
    while (b - a) / 2.0 > epsilon and iter_count < max_iter:
        c = (a + b) / 2.0  
        if f(c) == 0:  
            return c
        elif f(a) * f(c) < 0: 
            b = c
        else: 
            a = c
        iter_count += 1
    return (a + b) / 2.0  
a = 0.0
b = 1.0
root = bisection_method(a, b)
if root is not None:
    print(f"Təqribi kök: {root}")
