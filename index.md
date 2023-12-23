# Geometric Algebra Cheat Sheet

Identities and key results in Geometric Algebra that are useful to me and hopefully others 

## Geometric Product

Formula | Comment
:-----: | -------
$ab = a \cdot b + a \wedge b$ | Geometric product of two vectors $a$ and $b$
$a \cdot b = \frac{1}{2}\left( ab + ba\right)$ | Inner product of two vectors as symmetric part of geometric product
$a \wedge b = \frac{1}{2}\left( ab - ba\right)$ | Exterior product of two vectors as antisymmetric part of geometric product

## Multivectors

Identity | Comment
:------: | -------
$a_1 \wedge\dots\wedge a_r = \frac{1}{r!} \sum_{\mathcal{K}} (-1)^\epsilon a_{k_1} \dots a_{k_r}$ | Exterior product of $r$ vectors. $\mathcal{K}$ is the set of permutations of $1 \dots r$ and $\epsilon$ is even for even perms and odd for odd
$a_1 \wedge a_2 \wedge a_3 = \frac{1}{6} \left( a_1a_2a_3+a_3a_1a_2+a_2a_3a_1-a_1a_3a_2-a_2a_1a_3-a_3a_2a_1\right)$ | Example of the above for $r=3$. Note $a \wedge b = \frac{1}{2}\left( ab - ba\right)$ is example for $r=2$
$a \cdot A_r = a A_r - (-1)^rA_r a \qquad (*)$ | Prove by repeated application of $ab = 2a\cdot b - ba$ to $a a_1\dots a_r$ for orthogonal $\{a_i\}$
$a \wedge A_r = a A_r + (-1)^rA_r a \qquad (**)$ | Extends definition of $\wedge$ to multivectors
$aA_r = a\cdot A_r + a\wedge A_r$ | Combine above two formulae. $a\cdot A_r$ has grade $r-1$, $a\wedge A_r$ has grade $r+1$
$A_r\cdot(B_s\cdot C_t) = (A_r\wedge B_s)\cdot C_t \quad r+s\leq t \qquad (\triangleleft)$ | Prove by grade projection
$A_r\cdot(B_s\cdot C_t) = (A_r\cdot B_s)\cdot C_t \quad r+t\leq s \qquad (\triangleright)$ | Ditto
$a\cdot (a_1 \wedge\dots\wedge a_r) = \sum_{k=1}^r (-1)^{k+1} a\cdot a_k \; a_1 \wedge\dots\wedge \check a_k \wedge\dots\wedge a_r$ | The check on $\check a_k$ means "omit that term from the exterior product"

## Vectors and Bivectors

Identity | Comment
:------: | -------
$a\cdot(b\wedge c) = a\cdot b\;c - a\cdot c\;b$ | Simplest example of above identity, $r=2$
$a\cdot(a_1\wedge a_2\wedge a_3) = a\cdot a_1\;a_2\wedge a_3 - a\cdot a_2\;a_1\wedge a_3 + a\cdot a_3\;a_1\wedge a_2$ | Next simplest example, $r=3$
$(a\wedge b)\cdot B = a\cdot (b\cdot B)$ | Application of $(\triangleleft)$ in the case $r=s=1$ and $t=2$
$(a\cdot B) \cdot b = a\cdot(B\cdot b)$ | Application of $(\triangleright)$ in the case $r=t=1$ and $s=2$
$(a\wedge b)\cdot(c\wedge d) = b\cdot c\; a\cdot d - a\cdot c \; b\cdot d$ | Expand into geometric products and use $ab = 2a\cdot b - ba$
$a\cdot(b\wedge B) = a\cdot b\; B - b\wedge(a\cdot B)$ | Expand into geometic products using $(*)$ and $(**)$

## Commutator Product

Identity | Comment
:------: | -------
$M \times N = \frac{1}{2}(MN-NM)$ | Definition, for multivectors $M$ and $N$
$L\times(M\times N) + N\times(L\times M) + M\times(N\times L) = 0$ | Jacobi identity for multivectors $L$, $M$ and $N$
$B\times a = \frac{1}{2}(Ba-aB) = B \cdot a$ | Special case for bivector $B$ and vector $a$ using $(*)$
$B\times A_r = \langle B\times A_r\rangle_r$ | Commutator product with bivector is grade-preserving for blade $A_r$ and hence multivector $M$
$BA_r = B\cdot A_r + B\times A_r + B\wedge A_r$ | Therefore $\frac{1}{2}(BA_r + A_rB) = B\cdot A_r + B\wedge A_r$
$(a\wedge b)\times B = (a\cdot B)\wedge b + a\wedge (b\cdot B)$ | Expand into geometic products using $(**)$ and def'n of commutator product

## Pseudoscalar

Identity | Comment
:------: | -------
$I = e_1 \wedge\dots\wedge e_n$ | For orthonormal vectors $\{e_i \| i=1\dots n\}$
$I^2 = \pm1$ | Sign depends on metric but is typically -1 in physics applications
$IA_r = (-1)^r(n-1)A_rI$ | For blade $A_r$ in $n$-dims. $I$ always commutes with even-grade multivectors
$a\cdot (A_rI) = a\wedge A_r\, I$ | Using the above commutation rule together with $(*)$

## Linear Algebra

Identity | Comment
:------: | -------
$b = \mathsf F(a) $ | Linear function (whose components form a matrix)
$\mathsf F(\mu a + \nu b) = \mu\mathsf F(a) + \nu\mathsf F(b)$ | Linearity for vectors $a$ and $b$ and scalars $\mu$ and $\nu$
$\mathsf F(a\wedge b)=\mathsf F(a) \wedge \mathsf F(b)$ | Action on a bivector
$\mathsf F(\mu M + \nu N) = \mu \mathsf F(M) + \nu \mathsf F(N) \\ \mathsf F(A_r) = \langle\mathsf F(A_r)\rangle_r$ | Linearity and grade-preservation for multivectors $M$ and $N$, and blade $A_r$
$a\cdot\overline{\mathsf F}(b) = \mathsf F(a)\cdot b$ | Definition of $\overline{\mathsf F}$, the adjoint (transpose) of $\mathsf F$
$\langle A\,\overline{\mathsf F}(B)\rangle = \langle\mathsf F(A) \, B \rangle \qquad (\bullet)$ | Multivector version of above definition of adjoint
$A_r\cdot \overline{\mathsf F}(B_s) = \overline{\mathsf F}\left(\mathsf F(A_r)\cdot B_s\right) \qquad r\leq s \qquad $| Combine definition of adjoint with $(*)$, eg for $A_r = a$ and $B_s = b\wedge c$
$\mathsf F(A_r)\cdot B_s = \overline{\mathsf F}\left(A_r\cdot \overline{\mathsf F}(B_s)\right) \qquad r\geq s \qquad (\dagger)$ | Combine definition of adjoint with $(*)$, eg for $A_r = a\wedge b$ and $B_s = c$
$R = nm = \exp(-\hat B\theta/2) = \cos(\theta/2) - \hat B\sin(\theta/2)$ | Rotor $R$ from vectors $m$ and $n$ where $m\cdot n = \cos\theta$, $\hat B = \frac{m\wedge n}{\sin(\theta/2)}$ and $\hat B^2 = -1$
$\mathsf F(M) = RM\tilde R$ | Multivector $M$ rotated by angle $\theta$ in $\hat B$ plane

## Determinant and inverse

Identity | Comment
:------: | -------
$\mathsf F(I) = \det(\mathsf F)\, I$ | Definition of determinant, as volume scale factor for $\mathsf F$
$\det(\mathsf F\mathsf G)\,I = \det(\mathsf F)\det(\mathsf G)\, I$ | Because $\det(\mathsf F\mathsf G)\,I = \mathsf F\mathsf G(I) = \det(\mathsf G)\, \mathsf F(I) = \det(\mathsf F)\det(\mathsf G)\, I$ using the above definition
$\det(\mathsf F) = \det(\overline{\mathsf F})$ | Because $\det(\mathsf F) = \langle\mathsf F(I)I^{-1}\rangle = \langle I\overline{\mathsf F}(I^{-1})\rangle = \langle \overline{\mathsf F}(I^{-1})I\rangle = \det(\overline{\mathsf F})$ using $(\bullet)$
$\mathsf F^{-1}(M) = \frac{1}{\det(\mathsf F)} I \overline{\mathsf F}(I^{-1}M)$ | Inverse of $\mathsf F$. Holds also when $\mathsf F \rightarrow \overline{\mathsf F}$. From definition of determinant, multiply by arbitrary multivector $N$: $$\det(\mathsf F)IN = \mathsf F(I)N = \mathsf F\left(I\overline{\mathsf F}(N)\right)$$ using $(\dagger)$ and that $\mathsf F(I)\cdot N = \mathsf F(I)N$ and $I\cdot \overline{\mathsf F}(N) = I\overline{\mathsf F}(N)$. Now let $M = IN$ and apply $\mathsf F^{-1}$ to both sides.

---

[![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg