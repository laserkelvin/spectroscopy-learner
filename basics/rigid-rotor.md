# rigid-rotor


The rigid rotor is the basic approximation to computing the rotational motions of
molecules: we assume that the molecule does not distort as it rotates, and the
energy associated with rotation correspond with the moments of inertia of the molecule.

We start with the classical equations for angular momentum and energy, from [[gordy-cook]]
Chapter 1:

$$\bf{P} = \bf{I} \cdot \omega$$

with angular velocity $\omega$ and moment of inertia tensor $\bf{I}$; for a molecule in $xyz$ coordinates with atom masses $m$, the matrix elements are (taken again from [[gordy-cook]]):

![](images/2021-11-22-11-06-34.png)

A Python implementation would look like:

```python
# for an atom objects with mass and xyz coordinates
def i_xx(atoms: Atom) -> float:
    return sum([atom.mass * (atom.y**2 + atom.z**2) for atom in atoms])
```

...and the rest is history. Like everything else in nature, things are simpler when
this matrix is diagonal, which is found when the molecule is rotated to align with
its *principal axes*, where $xyz$ align with how the mass is distributed throughout
the molecule. If that's the case, the rotational energy is given by:

$$E_r = \frac{1}{2}I_x \omega_x^2 + \frac{1}{2}I_y \omega_y^2 + \frac{1}{2}I_z \omega_z^2$$

where $I_x, I_y$, and $I_z$ are the principal moments of inertia.