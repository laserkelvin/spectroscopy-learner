# Ray's asymmetry parameter

Measures how asymmetric a molecule is, ranging from -1 ([[prolate]]) to 1 ([[oblate]]) limits, with 0 being a perfectly asymmmetric top.

$$\kappa = \frac{2B - A - C}{A - C}$$

In Python:
```python
def kappa(A, B, C):
    return (2 * B - A - C) / (A - C)
```
