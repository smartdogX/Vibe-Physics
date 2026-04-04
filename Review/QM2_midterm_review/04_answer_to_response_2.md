# Answer to Response 2

1. $\ket{n_1,n_2,\dots,n_k,\dots}=(\hat{c}^{\dagger}_1)^n_1(\hat{c}^{\dagger}_2)^n_2\dots(\hat{c}^{\dagger}_k)^n_k\dots\ket{0}$
2. One-body operators: $\hat{H}_I=\sum_{kl}\hat{c}^{\dagger}_k\hat{c}_l$
3. $\hat{H} = -J\sum_{\sigma}\left(\hat{c}^{\dagger}_{\sigma L}\hat{c}_{\sigma R}+\hat{c}^{\dagger}_{\sigma R}\hat{c}_{\sigma L}\right)+\frac{U}{2}\left(\hat{n}_L\left(\hat{n}_L-1\right)+\hat{n}_R\left(\hat{n}_R-1\right)\right)$
4. $\ket{\uparrow,\uparrow}$ and $\ket{\downarrow,\downarrow}$, eigenenergy is 0.
5. $\ket{o^{\prime}_2}$ is the triplet, $\ket{o^{\prime}_1}$ gets the interaction energy U.
6. $\ket{e^{\prime}_1} = \frac{\ket{0,\uparrow\downarrow}+\ket{\uparrow\downarrow,0}}{\sqrt{2}}$,$\ket{e^{\prime}_2} = \frac{\ket{\uparrow,\downarrow}-\ket{\uparrow,\downarrow}}{\sqrt{2}}$, and $\hat{H}_{even}=\begin{pmatrix}U&-2J\\
-2J&0\end{pmatrix}$.
7. $\ket{e^{\prime}_2} = \frac{\ket{\uparrow,\downarrow}-\ket{\uparrow,\downarrow}}{\sqrt{2}}$, the triplet is not an eigenstate.
8. a. Because the two spin in triplet state not in one orbital.
b. For two fermions in the same orbital, it's obivously not the case.
9. Particle hole transformation: $\hat{U}=\prod\hat{c}^{\dagger}_{i\sigma}\hat{c}_{i^{\prime}\sigma^{\prime}}$.
For example, $\hat{U}\ket{\uparrow\downarrow,0}=\ket{0,\uparrow\downarrow}$.
10. particle-hole transformation operator $\hat{U}$.

---

# Feedback

Overall: this is a solid pass on the parity structure, but there are a few important corrections. The biggest issues are:
- you wrote the bosonic on-site interaction in Question 3 instead of the fermionic Fermi-Hubbard interaction,
- the singlet state in Questions 6 and 7 has a typo,
- the particle-hole transformation and the pseudospin generator got mixed together.

## Quick Grade

Approximate score: 5.5/10.

Strong:
- Question 4 is correct.
- Question 5 is correct.
- The even-sector matrix in Question 6 is correct.

Needs correction:
- Questions 1, 2, 3, 6, 7, 8, 9, 10.

## By Question

### 1.
Mostly correct, but incomplete.

You wrote the ordered Fock-state convention correctly up to notation, but the question also asked for the sign when the annihilation operator acts on an occupied orbital.

The key result you should remember is
\[
\hat c_k \ket{n_1,\dots,n_k=1,\dots}
=(-1)^{\sum_{j=1}^{k-1} n_j}
|n_1,\dots,n_k=0,\dots\rangle.
\]

### 2.
Incomplete.

You wrote only part of the one-body operator, and you omitted the coefficients. It should be
\[
\hat O_{1b}=\sum_{kl} o_{kl}\hat c_k^\dagger \hat c_l.
\]

The two-body operator was also requested:
\[
\hat O_{2b}=\frac12\sum_{klsr} o_{klsr}\hat c_k^\dagger \hat c_l^\dagger \hat c_r \hat c_s.
\]

### 3.
Incorrect.

You wrote the bosonic Hubbard interaction
\[
\frac{U}{2}\left[\hat n_L(\hat n_L-1)+\hat n_R(\hat n_R-1)\right],
\]
but for the two-site Fermi-Hubbard model the interaction term is
\[
U(\hat n_{L\uparrow}\hat n_{L\downarrow}+\hat n_{R\uparrow}\hat n_{R\downarrow}).
\]

So the full Hamiltonian is
\[
\hat H_{2FH}
=-J\sum_{\sigma=\uparrow,\downarrow}
\left(
\hat c_{L\sigma}^\dagger \hat c_{R\sigma}
+\hat c_{R\sigma}^\dagger \hat c_{L\sigma}
\right)
+U(\hat n_{L\uparrow}\hat n_{L\downarrow}+\hat n_{R\uparrow}\hat n_{R\downarrow}).
\]

Memory anchor:
- bosons: \( \frac{U}{2}n(n-1) \)
- fermions: \( U n_{\uparrow} n_{\downarrow} \)

### 4.
Correct.

\[
|\uparrow,\uparrow\rangle
\quad \text{and} \quad
|\downarrow,\downarrow\rangle
\]
are already eigenstates, and both have energy 0.

### 5.
Correct.

\[
|o_1'\rangle
=\frac{|0,\uparrow\downarrow\rangle-|\uparrow\downarrow,0\rangle}{\sqrt2},
\qquad
|o_2'\rangle
=\frac{|\uparrow,\downarrow\rangle+|\downarrow,\uparrow\rangle}{\sqrt2}.
\]

\[
|o_2'\rangle
\]
is the triplet, and
\[
|o_1'\rangle
\]
gets interaction energy \(U\).

### 6.
Half correct.

Your state
\[
|e_1'\rangle
=\frac{|0,\uparrow\downarrow\rangle+|\uparrow\downarrow,0\rangle}{\sqrt2}
\]
is correct.

But your second state has a typo. You wrote

\[
\frac{|\uparrow,\downarrow\rangle-|\uparrow,\downarrow\rangle}{\sqrt2},
\]
which is zero. It should be
\[
|e_2'\rangle
=\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}.
\]

Your matrix is correct:
\[
H_{\text{even}}
=\begin{pmatrix}
U & -2J \\
-2J & 0
\end{pmatrix}.
\]

### 7.
Almost right idea, but the same typo matters.

The approximate ground state for
\[
U \gg J > 0
\]
is
\[
|e_2'\rangle
=\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2},
\]
which is the spin singlet.

Why is it not a triplet?
- The triplet sector does not get the same virtual hopping energy lowering.
- The singlet mixes with doubly occupied states and is pushed lower in energy.

So the better short answer is:
for large repulsive \(U\), one fermion sits on each site, but the lowest spin state is the singlet, not the triplet.

### 8a.
Partially correct, but too vague.

A sharper version is:
triplets avoid the contact interaction because the spatial/orbital part is antisymmetric, so the wave function vanishes when the two particles coincide.

### 8b.
Incorrect / too unclear.

The key point is:
- site inversion swaps left and right labels,
- particle exchange swaps the two identical particles.

These are different operations.

For example, site inversion acts as
\[
L \leftrightarrow R,
\]
while particle exchange acts as
\[
1 \leftrightarrow 2.
\]

Those are not the same symmetry.

### 9.
Incorrect.

For the two-site model, the particle-hole transformation is written in terms of new hole operators:
\[
\hat d_{L\sigma}^\dagger = \hat c_{L\sigma},
\qquad
\hat d_{L\sigma} = \hat c_{L\sigma}^\dagger,
\]
\[
\hat d_{R\sigma}^\dagger = -\hat c_{R\sigma},
\qquad
\hat d_{R\sigma} = -\hat c_{R\sigma}^\dagger.
\]

It relates:
- the 0-particle sector to the 4-particle sector,
- the 1-particle sector to the 3-particle sector,
- and leaves the 2-particle sector mapped to itself.

### 10.
Incorrect.

The operator that changes the energy by plus or minus \(U\) and generates the pseudospin towers is not the particle-hole operator.

It is the pseudospin raising/lowering operator:
\[
\hat \Upsilon_+
\quad \text{and} \quad
\hat \Upsilon_-.
\]

The key commutator is
\[
[\hat H_{FH},\hat \Upsilon_\pm]=\pm U \hat \Upsilon_\pm.
\]

That is why repeated action of
\[
\hat \Upsilon_+
\]
builds the pseudospin tower.

## Most Important Corrections To Memorize

1. Fermi-Hubbard interaction term:
\[
U(\hat n_{L\uparrow}\hat n_{L\downarrow}+\hat n_{R\uparrow}\hat n_{R\downarrow}).
\]

2. Singlet:
\[
\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}.
\]

3. Triplet with \(m_S=0\):
\[
\frac{|\uparrow,\downarrow\rangle+|\downarrow,\uparrow\rangle}{\sqrt2}.
\]

4. Particle-hole transformation is not the same thing as the pseudospin ladder operator.

## Mini Retry

Try these again from memory in 1-2 lines each:

1. Write the correct two-site Fermi-Hubbard Hamiltonian.
2. Write \( |e_2'\rangle \) and \( |o_2'\rangle \).
3. State the particle-hole transformation for left and right operators.
4. Name the operator that generates the pseudospin tower.
