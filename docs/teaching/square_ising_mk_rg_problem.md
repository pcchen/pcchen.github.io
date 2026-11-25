# Real-space RG for the 2D Ising model on a square lattice with Migdal–Kadanoff approximation

## Migdal–Kadanoff approximation

Consider the ferromagnetic Ising model on a two-dimensional square lattice,

$$
H=-J\sum_{\langle ij\rangle}s_i s_j,\qquad s_i=\pm1,\quad J>0,
$$

with partition function

$$
Z(K)=\sum_{\{s_i\}}\exp\left(K\sum_{\langle ij\rangle}s_i s_j\right),\qquad K=\frac{J}{k_BT}.
$$

We construct an approximate real-space renormalization group (RG) transformation using the Migdal–Kadanoff bond-moving approximation, with length rescaling factor $b=2$.

## (a) Bond moving

Choose the sites marked `●` as the retained spins. The remaining sites, marked `○`, will be eliminated. The following schematic shows a portion of the original lattice:

```text
●───○───●───○───●
│   │   │   │   │
○───○───○───○───○
│   │   │   │   │
●───○───●───○───●
│   │   │   │   │
○───○───○───○───○
│   │   │   │   │
●───○───●───○───●
```

All original bonds have coupling $K$. Move the horizontal bonds from odd rows to adjacent even rows, and the vertical bonds from odd columns to adjacent even columns. In the bulk, this produces two parallel bonds on each surviving link:

```text
●═══○═══●═══○═══●
║       ║       ║
○   ○   ○   ○   ○
║       ║       ║
●═══○═══●═══○═══●
║       ║       ║
○   ○   ○   ○   ○
║       ║       ║
●═══○═══●═══○═══●
```

Double lines denote two parallel bonds. Isolated spins contribute only a constant factor to the partition function. The diagrams depict a bulk patch, with boundary effects omitted.

1. Show that combining two parallel Ising bonds of coupling $K$ gives an effective coupling $\widetilde K=2K$.
2. Explain why bond moving is an approximation rather than an exact transformation.
3. Generalize the bond-moving prescription to a $d$-dimensional hypercubic lattice with integer rescaling factor $b$. Show that $\widetilde K=b^{d-1}K$.

## (b) Decimation

Consider three consecutive spins connected by the strengthened bonds obtained in part (a). Trace out the intermediate spin:

```text
       2K      2K
   ●════════○════════●
   s₁       s₂       s₃

       trace over s₂
            ↓

   ●─────────────────●
   s₁       K′       s₃
```

$$
\sum_{s_2=\pm1}e^{\widetilde K(s_1s_2+s_2s_3)}=Ae^{K's_1s_3}.
$$

1. Determine $A$ and $K'$ by considering $s_1=s_3$ and $s_1=-s_3$.
2. Show that $K'=\frac12\ln\cosh(2\widetilde K)$.
3. Hence obtain the Migdal–Kadanoff RG recursion relation:

    $$
    \boxed{K'=\frac12\ln\cosh(4K).}
    $$

After decimation, the renormalized lattice is again a square lattice, now with spacing $a'=2a$ and nearest-neighbor coupling $K'$:

```text
●───────●───────●
│       │       │
│       │       │
│       │       │
●───────●───────●
│       │       │
│       │       │
│       │       │
●───────●───────●
```

## (c) Fixed points and RG flow

Let $K'=R(K)$ denote the RG recursion relation.

1. Determine the fixed points satisfying $K^*=R(K^*)$, including the infinite-coupling limit.
2. Find the nontrivial fixed point $K_c^{\mathrm{MK}}$ numerically.
3. Sketch $R(K)$ together with the line $K'=K$, and indicate the direction of the RG flow.
4. Identify the stable and unstable fixed points and explain their physical significance in terms of the ordered and disordered phases.
5. Estimate the critical temperature $k_BT_c^{\mathrm{MK}}/J=1/K_c^{\mathrm{MK}}$ and compare it with Onsager's exact result,

    $$
    K_c^{\mathrm{exact}}=\frac12\ln(1+\sqrt{2}).
    $$

## (d) Linearization and critical exponents

Consider a small deviation from the nontrivial fixed point, $K=K_c^{\mathrm{MK}}+\delta K$.

1. Linearize the recursion relation to obtain $\delta K'=\lambda_t\delta K+O(\delta K^2)$ and calculate

    $$
    \lambda_t=\left.\frac{dR}{dK}\right|_{K=K_c^{\mathrm{MK}}}.
    $$

2. Using $\lambda_t=b^{y_t}$, determine the thermal scaling exponent $y_t$.
3. Starting from the RG transformation of the correlation length (measured in lattice units), $\xi(K')=\xi(K)/b$, show that

    $$
    \boxed{\nu=\frac{\ln b}{\ln\lambda_t}.}
    $$

4. Calculate $\nu$ numerically and compare it with the exact two-dimensional Ising exponent $\nu=1$.
5. Assuming hyperscaling, estimate the specific-heat exponent $\alpha=2-d\nu$.

## (e) Generalization to arbitrary dimension

1. For an arbitrary integer rescaling factor $b$, show that decimation of a chain of $b$ strengthened bonds yields

    $$
    \boxed{\tanh K'=\left[\tanh\left(b^{d-1}K\right)\right]^b.}
    $$

2. Specialize to $d=1$ and $b=2$. Explain why there is no finite-temperature phase transition.
3. Specialize to $d=3$ and $b=2$. Numerically estimate $K_c$ and $\nu$.
4. Discuss the advantages and limitations of the Migdal–Kadanoff approximation.

## (f) Optional: Order of bond moving and decimation

An alternative implementation performs series decimation before combining parallel bonds.

1. Show that this prescription leads to $K'=\ln\cosh(2K)$ for $d=2$ and $b=2$.
2. Calculate the nontrivial fixed point and the correlation-length exponent for this alternative recursion relation.
3. Explain why the two prescriptions predict different critical temperatures but identical correlation-length exponents.
4. Show that the two RG transformations are related by a rescaling of the coupling constant.
