# Particle-Hole Symmetry

This note focuses on the particle-hole transformation in the Fermi-Hubbard model, why it works, what it does to the states, and how it is related to the pseudospin symmetry.

## 1. Core Idea

The phrase "particle-hole transformation" means:
- instead of describing the system by where particles are present,
- we describe it by where particles are missing relative to a fully filled reference state.

For fermions this is natural, because each orbital can only be:
- empty, or
- occupied once.

So an empty orbital can be interpreted as a hole.

This is different from bosons. For bosons, a site can contain arbitrarily many particles, so there is no unique "fully filled" reference state.

## 2. Why Holes Behave Like Particles

For the two-site model, the vacuum state is
\[
|0\rangle,
\]
while the fully filled state is
\[
|\uparrow\downarrow,\uparrow\downarrow\rangle.
\]

If we remove one fermion from the filled state, what remains is one hole.

So:
- particle language starts from the vacuum and adds particles with creation operators,
- hole language starts from the filled state and creates holes by removing particles.

This is why a hole creation operator is built from a particle annihilation operator.

## 3. Two-Site Particle-Hole Transformation

For the two-site noninteracting model, the book defines the hole operators by
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

### 3.1 Particle-hole transformation operator

It is useful to distinguish:
- the transformed operators,
- and the operator that implements the transformation.

For a bipartite lattice, the book gives the transformation operator as
\[
\hat U_{\mathrm{ph}}
=\prod_{i,\sigma}
\left(
\hat c_{i\sigma}
+\eta_i \hat c_{i\sigma}^\dagger
\right),
\]
with
\[
\eta_i =\begin{cases}
+1, & i \in A, \\
-1, & i \in B.
\end{cases}
\]

This operator implements the particle-hole map by conjugation:
\[
\hat d_{i\sigma}^\dagger
=\hat U_{\mathrm{ph}}
\hat c_{i\sigma}^\dagger
\hat U_{\mathrm{ph}}^\dagger
=\eta_i \hat c_{i\sigma},
\]
\[
\hat d_{i\sigma}
=\hat U_{\mathrm{ph}}
\hat c_{i\sigma}
\hat U_{\mathrm{ph}}^\dagger
=\eta_i \hat c_{i\sigma}^\dagger.
\]

For the two-site model, we can specialize this by taking
\[
\eta_L = +1,
\qquad
\eta_R = -1.
\]

Then one convenient form is
\[
\hat U_{\mathrm{ph}}^{(2\text{-site})}
=\left(\hat c_{L\uparrow}+\hat c_{L\uparrow}^\dagger\right)
\left(\hat c_{L\downarrow}+\hat c_{L\downarrow}^\dagger\right)
\left(\hat c_{R\uparrow}-\hat c_{R\uparrow}^\dagger\right)
\left(\hat c_{R\downarrow}-\hat c_{R\downarrow}^\dagger\right),
\]
up to a fixed choice of ordering convention for the fermionic factors.

The ordering matters because fermionic operators anticommute. In practice:
- choose one ordering in the product,
- keep it fixed throughout the calculation,
- and the transformation is then well defined up to an overall phase convention.

The minus sign on the right site is important. It is chosen so that the hopping Hamiltonian keeps the same form after the transformation.

The two-site noninteracting Hamiltonian is
\[
\hat H_0
=-J\sum_{\sigma=\uparrow,\downarrow}
\left(
\hat c_{L\sigma}^\dagger \hat c_{R\sigma}
+\hat c_{R\sigma}^\dagger \hat c_{L\sigma}
\right).
\]

After the particle-hole transformation, it has the same structure in terms of the hole operators. That is the symmetry.

## 4. Occupation Numbers Under the Transformation

The transformation sends
\[
\hat n_{L\sigma} \to 1-\hat n_{L\sigma},
\qquad
\hat n_{R\sigma} \to 1-\hat n_{R\sigma}.
\]

So:
- occupied becomes empty,
- empty becomes occupied.

This is why it is called particle-hole transformation.

A very useful memory anchor is:
\[
\text{particle} \leftrightarrow \text{absence of particle in the filled state}.
\]

## 5. How the Particle Sectors Map

For the two-site model there are four single-particle orbitals:
- L up,
- L down,
- R up,
- R down.

So the maximum particle number is 4.

Under particle-hole symmetry:
- the 0-particle sector maps to the 4-particle sector,
- the 1-particle sector maps to the 3-particle sector,
- the 2-particle sector maps to itself.

This is why the spectra for:
- 0 and 4 particles,
- 1 and 3 particles,

are related.

In the noninteracting two-site model, the 1-particle and 3-particle spectra are actually identical, and the 0-particle and 4-particle sectors both have zero energy.

## 6. Why the Two-Particle Sector Maps to Itself

The total number of orbitals is 4, so a state with 2 particles has 2 holes.

That means:
\[
N=2 \quad \longleftrightarrow \quad 4-N=2.
\]

So the two-particle sector is special: it is self-dual under particle-hole symmetry.

That is one reason the two-particle sector is so important in the two-site Fermi-Hubbard problem.

## 7. Interacting Two-Site Fermi-Hubbard Model

The interacting two-site Hamiltonian is
\[
\hat H_{2FH}
=-J\sum_{\sigma=\uparrow,\downarrow}
\left(
\hat c_{L\sigma}^\dagger \hat c_{R\sigma}
+\hat c_{R\sigma}^\dagger \hat c_{L\sigma}
\right)
+U
\left(
\hat n_{L\uparrow}\hat n_{L\downarrow}
+\hat n_{R\uparrow}\hat n_{R\downarrow}
\right).
\]

The interaction term is not strictly invariant in the same simple sense as the kinetic term, because under
\[
\hat n_{i\sigma} \to 1-\hat n_{i\sigma},
\]
the doublon-counting term changes.

This is why, in the interacting model:
- the 3-particle energies are the 1-particle energies shifted by U,
- the 4-particle energy is the vacuum energy shifted by 2U.

So the particle-hole transformation still gives a strong relation between sectors, but now with an energy shift coming from the interaction energy of the filled state.

## 8. General Bipartite-Lattice Transformation

For the many-site Fermi-Hubbard model on a bipartite lattice, the transformation generalizes to
\[
\hat d_{i\sigma}^\dagger = \eta_i \hat c_{i\sigma},
\qquad
\hat d_{i\sigma} = \eta_i \hat c_{i\sigma}^\dagger,
\]
where
\[
\eta_i =\begin{cases}
+1, & i \in A, \\
-1, & i \in B.
\end{cases}
\]

Here A and B are the two sublattices.

This sign pattern is the many-site version of the left/right sign choice in the two-site problem.

It is needed so that nearest-neighbor hopping between opposite sublattices keeps the right form.

The same transformation is implemented by the operator
\[
\hat U_{\mathrm{ph}}
=\prod_{i,\sigma}
\left(
\hat c_{i\sigma}
+\eta_i \hat c_{i\sigma}^\dagger
\right).
\]

So when you want the most compact statement of particle-hole symmetry, the pair of formulas to remember is:
\[
\hat d_{i\sigma}^\dagger = \eta_i \hat c_{i\sigma},
\qquad
\hat d_{i\sigma} = \eta_i \hat c_{i\sigma}^\dagger,
\]
together with
\[
\hat U_{\mathrm{ph}}
=\prod_{i,\sigma}
\left(
\hat c_{i\sigma}
+\eta_i \hat c_{i\sigma}^\dagger
\right).
\]

## 9. What Happens to the Spectrum in the Many-Site Model

For a bipartite lattice with V sites, the particle-hole transformation relates the spectrum at
\[
(N_\uparrow,N_\downarrow)
\]
to the spectrum at
\[
(V-N_\uparrow, V-N_\downarrow).
\]

The relation given in the book is
\[
E_\alpha(V,N_\uparrow,N_\downarrow)
=E_\alpha(V,V-N_\uparrow,V-N_\downarrow)
+U(N_\uparrow+N_\downarrow-V).
\]

This is an extremely useful formula.

It says:
- the energies are not usually identical,
- but they are tied together by a simple interaction-dependent shift.

## 10. Half Filling

Half filling means
\[
N_\uparrow = N_\downarrow = \frac{V}{2}.
\]

At half filling, the transformed particle numbers are the same as the original ones:
\[
V-N_\uparrow = N_\uparrow,
\qquad
V-N_\downarrow = N_\downarrow.
\]

So the model maps back to itself.

This is why half filling is special:
- it is the natural fixed point of particle-hole symmetry.

## 11. Relation to Spin Symmetry and Pseudospin Symmetry

This is the part that is easiest to mix up.

### 11.1 Spin symmetry

The usual spin operators act on the real spin degree of freedom:
- up spin,
- down spin.

They organize states into singlets and triplets.

### 11.2 Pseudospin symmetry

On a bipartite lattice, one can define another SU(2), called pseudospin.

The book defines the pseudospin operators so that
\[
[\hat \Upsilon_+,\hat \Upsilon_-]=2\hat \Upsilon_z,
\qquad
[\hat \Upsilon_z,\hat \Upsilon_\pm]=\pm \hat \Upsilon_\pm.
\]

The important physical meaning is:
- the operator shown with a plus sign creates a pair,
- the operator shown with a minus sign removes a pair,
- they change particle number by 2.

Also,
\[
[\hat H_{FH},\hat \Upsilon_\pm] = \pm U \hat \Upsilon_\pm.
\]

So acting with the pseudospin raising or lowering operator moves you up or down a pseudospin tower, shifting the energy by plus or minus U.

### 11.3 Where particle-hole comes in

The book states that the spin operators and the pseudospin operators are related by a particle-hole transformation on the down-spin fermions.

That means:
- particle-hole symmetry is the bridge,
- pseudospin is the symmetry structure that appears after making that bridge.

At half filling, this becomes especially powerful and leads to an additional
\[
SU(2)\times SU(2)
\]
structure.

## 12. Particle-Hole Transformation Is Not the Same as the Pseudospin Ladder

This is a very important distinction.

The particle-hole transformation:
- is a symmetry transformation,
- rewrites particles as holes,
- maps one particle-number sector to another.

The pseudospin ladder operators:
- are operators inside the Hilbert space,
- add or remove pairs,
- generate towers of states whose energies differ by U.

So:
- particle-hole transformation is not the same thing as the pseudospin raising or lowering operator,
- but it helps explain why pseudospin symmetry exists.

## 13. Why This Symmetry Is Useful on an Exam

Particle-hole symmetry helps you:
- relate 1-particle and 3-particle sectors without diagonalizing both,
- relate empty and filled sectors,
- understand why half filling is special,
- remember why the many-site Hubbard model has extra structure on bipartite lattices,
- avoid confusing spin SU(2) with pseudospin SU(2).

## 14. Fast Summary

### Main picture

A hole is an empty fermionic orbital measured relative to the fully filled state.

### Two-site map

\[
\hat d_{L\sigma}^\dagger = \hat c_{L\sigma},
\qquad
\hat d_{R\sigma}^\dagger = -\hat c_{R\sigma}.
\]

and similarly for the annihilation operators.

### Transformation operator

\[
\hat U_{\mathrm{ph}}
=\prod_{i,\sigma}
\left(
\hat c_{i\sigma}
+\eta_i \hat c_{i\sigma}^\dagger
\right).
\]

### Occupation mapping

\[
\hat n_{i\sigma} \to 1-\hat n_{i\sigma}.
\]

### Sector mapping in the two-site model

\[
0 \leftrightarrow 4,
\qquad
1 \leftrightarrow 3,
\qquad
2 \leftrightarrow 2.
\]

### Many-site bipartite map

\[
\hat d_{i\sigma}^\dagger = \eta_i \hat c_{i\sigma},
\qquad
\eta_i = \pm 1
\]
depending on sublattice.

### Energy relation

\[
E_\alpha(V,N_\uparrow,N_\downarrow)
=E_\alpha(V,V-N_\uparrow,V-N_\downarrow)
+U(N_\uparrow+N_\downarrow-V).
\]

### Half filling

\[
N_\uparrow=N_\downarrow=\frac{V}{2}
\]
is the fixed point of particle-hole symmetry.

### Most common confusion

Do not confuse:
- particle-hole transformation,
- spin singlet/triplet structure,
- pseudospin ladder operators.

They are related, but they are not the same thing.

## 15. Memory Anchors

- Particle language starts from the vacuum.
- Hole language starts from the filled state.
- Empty becomes occupied, occupied becomes empty.
- In the two-site model, 1 particle and 3 particles are mirror sectors.
- Half filling is special because particle-hole sends the system back to itself.
- Pseudospin towers are generated by the pseudospin ladder operators, not by the particle-hole transformation itself.
