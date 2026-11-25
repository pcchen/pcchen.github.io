# Problem: Real-Space Renormalization Group for the Triangular-Lattice Ising Model

Consider the ferromagnetic Ising model on a two-dimensional triangular lattice,

$$H=-J\sum_{\langle ij\rangle}\sigma_i\sigma_j,\qquad \sigma_i=\pm1,\quad J>0,$$

where the sum runs over all nearest-neighbor pairs. The partition function is

$$Z(K)=\sum_{\{\sigma\}}\exp\left(K\sum_{\langle ij\rangle}\sigma_i\sigma_j\right),\qquad K=\frac{J}{k_BT}.$$

In this problem, we construct a real-space renormalization group (RG) transformation using the majority-rule block-spin transformation and the cumulant expansion.

## (a) Block-spin transformation

Divide the triangular lattice into non-overlapping triangular blocks, each containing three nearest-neighbor spins. Denote the spins in block $I$ by $\sigma_{I,1},\sigma_{I,2},\sigma_{I,3}$.

The following diagram shows two neighboring triangular blocks (a portion of the original lattice). The solid lines denote intra-block bonds, and the dotted lines denote inter-block bonds. Other sites and bonds are omitted for clarity.

```text
                J3
               /  \
              /    \
    I3......J1------J2
   /  \    :
  /    \  :
I1------I2

  Block I     Block J
```

Under coarse graining, each triangle is replaced by a single spin:

```text
       I3
      /  \
     /    \      majority rule
   I1------I2  ----------------->  S_I
```

The resulting block-spin lattice has the following connectivity (shown around a central block):

```text
      S_1------S_2
     /   \    /   \
    /     \  /     \
 S_6------S_I------S_3
    \     /  \     /
     \   /    \   /
      S_5------S_4
```

Define a block spin $S_I=\pm1$ according to the majority rule,

$$S_I=\operatorname{sgn}(\sigma_{I,1}+\sigma_{I,2}+\sigma_{I,3}).$$

1. Draw the original lattice and the resulting block-spin lattice.
2. Show that the block spins form another triangular lattice.
3. Determine the length rescaling factor $b=a'/a$.

Define the projection operator

$$P_I(S_I,\{\sigma_I\})=\delta_{S_I,\operatorname{sgn}(\sum_{\alpha=1}^{3}\sigma_{I,\alpha})}.$$

Write down the exact expression for the renormalized Hamiltonian $H'[\{S\}]$ in terms of this projection operator, and show that the partition function is preserved under the transformation.

## (b) Intra-block and inter-block interactions

Decompose the dimensionless Hamiltonian as

$$-\beta H=A_0+V,$$

where

$$A_0=K\sum_I(\sigma_{I,1}\sigma_{I,2}+\sigma_{I,2}\sigma_{I,3}+\sigma_{I,3}\sigma_{I,1})$$

contains the intra-block interactions, and $V$ contains all inter-block nearest-neighbor interactions.

For a fixed block spin $S_I$, define the constrained single-block partition function

$$z_0(S_I)=\sum_{\{\sigma_I\}}P_I(S_I,\{\sigma_I\})e^{K(\sigma_{I,1}\sigma_{I,2}+\sigma_{I,2}\sigma_{I,3}+\sigma_{I,3}\sigma_{I,1})}.$$

1. Evaluate $z_0(S_I)$ explicitly.
2. Show that it is independent of $S_I$.
3. Show that the constrained expectation value of a microscopic spin can be written as

   $$ \langle\sigma_{I,\alpha}\rangle_{0,S_I}=m(K)S_I. $$

   Determine the function $m(K)$.

4. Calculate the intra-block correlation function

   $$ \langle\sigma_{I,\alpha}\sigma_{I,\gamma}\rangle_{0,S_I}=c(K),\qquad \alpha\ne\gamma. $$

## (c) Cumulant expansion

Introduce a parameter $\epsilon$ multiplying the inter-block interaction, such that

$$-\beta H=A_0+\epsilon V.$$

Define the constrained expectation value

$$\langle X\rangle_{0,\{S\}}=\frac{\sum_{\{\sigma\}}X e^{A_0}\prod_I P_I}{\sum_{\{\sigma\}}e^{A_0}\prod_I P_I}.$$

Show that the renormalized Hamiltonian satisfies

$$-\beta H'[\{S\}]=N_b\ln z_0+\ln\left\langle e^{\epsilon V}\right\rangle_{0,\{S\}},$$

where $N_b$ is the number of blocks.

Expand this expression up to second order in $\epsilon$, using the cumulant expansion.

Explain why the expectation values of microscopic spins belonging to different blocks factorize under the unperturbed ensemble.

## (d) First-order RG recursion relation

Retain only the first cumulant and set $\epsilon=1$.

Using the geometry of the triangular lattice, show that two nearest-neighbor blocks are connected by two microscopic bonds.

Derive the effective Hamiltonian

$$-\beta H'=C(K)+K'\sum_{\langle IJ\rangle}S_IS_J$$

and obtain the RG recursion relation

$$K'=R(K).$$

Express $R(K)$ explicitly in terms of $K$.

## (e) Fixed points and RG flows

Using the recursion relation obtained in part (d):

1. Find all fixed points in the ferromagnetic regime, $K\geq0$ (including the zero-temperature limit).
2. Determine their stability.
3. Sketch the RG flow in the parameter space.
4. Estimate the critical temperature $T_c$ and compare it with the exact result for the triangular-lattice Ising model,

   $$\frac{k_BT_c^{\mathrm{exact}}}{J}=\frac{4}{\ln3}.$$

## (f) Correlation-length critical exponent

Let $K^*$ denote the nontrivial fixed point.

Linearize the RG transformation around $K^*$ and show that

$$K'-K^*=\lambda_t(K-K^*)+O((K-K^*)^2).$$

Calculate the thermal scaling eigenvalue $\lambda_t$.

Using the scaling relation for the correlation length (measured in lattice units),

$$\xi(K')=\frac{\xi(K)}{b},$$

derive an expression for the correlation-length exponent $\nu$ in terms of $\lambda_t$ and $b$.

Evaluate $\nu$ numerically and compare it with the exact Ising exponent $\nu=1$.

## (g) Second-order cumulant — advanced question

Consider two microscopic inter-block bonds,

$$v_1=K\sigma_{I,\alpha}\sigma_{J,\gamma},\qquad v_2=K\sigma_{J,\delta}\sigma_{L,\eta},$$

where $I,J,L$ are three distinct blocks.

Calculate their connected correlation function,

$$\langle v_1v_2\rangle_0-\langle v_1\rangle_0\langle v_2\rangle_0,$$

for the two cases:

1. $\gamma=\delta$;
2. $\gamma\ne\delta$.

Discuss what types of effective interactions are generated by the second cumulant. Is the nearest-neighbor Ising Hamiltonian closed under the RG transformation?
