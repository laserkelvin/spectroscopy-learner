# Centrifugal distortion

Building on top of the [[rigid-rotor]] approximation, we get a more "realistic" picture of a rotating object by including centrifugal distortion: the shape of an object changes with more and more rotation, thereby affecting the spacing between energy levels.

## The distortable rotor

## Reduced Hamiltonian

See Watson's[^1] incredibly extensive paper on the matter; this is a heavily abridged version! The basic principle is that the full centrifugal distortion Hamiltonian ($\tau$) contains terms that are *arbitrary* and can be removed from consideration, substantially simplifying the problem.

This observation follows from the fact that the operators for angular momentum commute with one another (i.e. $\bf{J}_a\bf{J}_b = \bf{J}_b\bf{J}_a$), which ultimately means coefficients/terms in the Hamiltonian are non-unique and change depend on notation, and some terms are not separable from others (e.g. $\tau_{\alpha\beta\alpha\beta}$ and $\tau_{\alpha\alpha\beta\beta}$). The goal of a *reduced Hamiltonian* is to remove these depedencies; we can design unitary transformations to the Hamiltonian that project out/eliminate terms that are indeterminable. 

The transformation is designed to preserve all the nice properties of angular momentum operators: being Hermitian; time-reversal symmetry; functions of the principal axes. Providing a very condensed version here, we can factorize/break up the transformation $U$ into individual components:

$$U=\exp{iS_1}\exp{iS_3}\ldots$$

where $S_n$ has matrix elements:

$$S_n = \sum_{p+q+r=n} s_{pqr}(J_x^pJ_y^qJ_z^r + J_z^rJ_y^qJ_x^p)$$

with real coefficients $s_{pqr}$, and the same angular momentum operators $J_{x,y,z}$ as the unperturbed Hamiltonian. We can then express the distortable Hamiltonian generally with:

$$H_{2m+2} = \exp(-iS_{2m+1})H_{2m}\exp(iS_{2m+1})$$

with $m=0,1,2,\ldots$, with $H_0$ as the unperturbed Hamiltonian, and $H_\infty=\tilde{H}$, the complete Hamiltonian. The centrifugal distortion terms that we know and love follow this power series, which go as quartic ($m=1$), sextic ($m=2$), octic ($m=3$), etc. The prime example given by Watson for the quartic terms starts from page 1940; the choice of which terms to eliminate is first deliberated, with the particularly important result of ending up with only *five* separable terms&mdash;which five depends on how the reduction is done exactly, and Watson discusses two cases which keep the Hamiltonian diagonal; the $A$ and $S$-reductions.

Because modern programs solve the rotational Hamiltonian in a symmetric-top basis, the choice of reduction is not typically so important anymore: in either case it is only a matter of including more basis functions to help convergence of the energy levels. The coefficients determined *are* dependent on the reduction chosen, and so it is important to stay consistent; which reduction is not important.

|Reduction | $A$  | $S$  |
|---|---|---|
| Quartic |  $\Delta_J$ |  $D_J$ |
| | $\Delta_{JK}$ | $D_{JK}$ |
| | $\Delta_{K}$ | $D_K$ |
| | $\delta_J$ | $d_1$ |
| | $\delta_K$ | $d_2$ |


[^1]: Watson, J. K. G. Determination of Centrifugal Distortion Coefficients of Asymmetric‐Top Molecules. The Journal of Chemical Physics 1967, 46 (5), 1935–1949. https://doi.org/10.1063/1.1840957.
