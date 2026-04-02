# Response 2

Following the updated project rules, this review focuses only on the Fermi-Hubbard part of Chapter 13 and stays retrieval-based.

**What Matters Most**
- Canonical algebra and ordered Fock convention:
\[
\{ \hat c_k,\hat c_l^\dagger \}=\delta_{kl}, \qquad
\{ \hat c_k,\hat c_l \}=0, \qquad
\{ \hat c_k^\dagger,\hat c_l^\dagger \}=0.
\]
- Book convention for fermionic Fock states:
\[
|n_1,n_2,\dots,n_k,\dots\rangle
=
(\hat c_1^\dagger)^{n_1}(\hat c_2^\dagger)^{n_2}\cdots(\hat c_k^\dagger)^{n_k}\cdots|0\rangle.
\]
- Acting with the annihilation or creation operator brings a sign:
\[
(-1)^{\sum_{j<k} n_j}.
\]
- One-body operator:
\[
\hat O_{1b}=\sum_{kl} o_{kl}\hat c_k^\dagger \hat c_l.
\]
- Two-body operator:
\[
\hat O_{2b}=\frac12 \sum_{klsr} o_{klsr}\hat c_k^\dagger \hat c_l^\dagger \hat c_r \hat c_s.
\]
- The exchange term for fermions carries a minus sign relative to bosons.
- Two-site Fermi-Hubbard Hamiltonian:
\[
\hat H_{2FH}
=
-J\sum_{\sigma=\uparrow,\downarrow}
(\hat c_{L\sigma}^\dagger \hat c_{R\sigma}+\hat c_{R\sigma}^\dagger \hat c_{L\sigma})
+U(\hat n_{R\uparrow}\hat n_{R\downarrow}+\hat n_{L\uparrow}\hat n_{L\downarrow}).
\]
- Only opposite-spin doublons feel the interaction energy U:
\[
|0,\uparrow\downarrow\rangle
\quad \text{and} \quad
|\uparrow\downarrow,0\rangle.
\]
- Main symmetry reductions: conservation of up-spin number, down-spin number, site inversion parity, and total spin. On bipartite lattices: particle-hole and pseudospin.

**Fast Distinctions**
- Site inversion L <-> R is not particle exchange.
- Singlet/triplet refers to spin symmetry, not left-right parity.
- Odd/even parity under L <-> R is separate from antisymmetric/symmetric under particle exchange.
- The triplets with
\[
m_S=\pm 1
\]
are
\[
|\uparrow,\uparrow\rangle
\quad \text{and} \quad
|\downarrow,\downarrow\rangle.
\]
- The triplet with
\[
m_S=0
\]
is
\[
\frac{|\uparrow,\downarrow\rangle+|\downarrow,\uparrow\rangle}{\sqrt2}.
\]
- The singlet is
\[
\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}.
\]

**Compact Derivation Chain**
- Start in the two-particle sector.
- Because the up-spin and down-spin particle numbers are conserved,
\[
|\uparrow,\uparrow\rangle
\quad \text{and} \quad
|\downarrow,\downarrow\rangle
\]
already decouple and have energy 0.
- The remaining basis is
\[
|0,\uparrow\downarrow\rangle,\quad
|\downarrow,\uparrow\rangle,\quad
|\uparrow,\downarrow\rangle,\quad
|\uparrow\downarrow,0\rangle.
\]
- Use site inversion parity.
- Odd basis:
\[
|o'_1\rangle=\frac{|0,\uparrow\downarrow\rangle-|\uparrow\downarrow,0\rangle}{\sqrt2},
\qquad
|o'_2\rangle=\frac{|\uparrow,\downarrow\rangle+|\downarrow,\uparrow\rangle}{\sqrt2}.
\]
- The state shown first above has energy U.
- The state shown second above has energy 0 and is the triplet with
\[
m_S=0.
\]
- Even basis:
\[
|e'_1\rangle=\frac{|0,\uparrow\downarrow\rangle+|\uparrow\downarrow,0\rangle}{\sqrt2},
\qquad
|e'_2\rangle=\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}.
\]
- In this basis,
\[
H_{\text{even}}=
\begin{pmatrix}
U & -2J \\
-2J & 0
\end{pmatrix}.
\]
- Therefore,
\[
E_\pm = \frac{U}{2}\pm \frac12\sqrt{U^2+16J^2}.
\]
- For
\[
U \gg J > 0,
\]
the ground state is approximately the spin singlet with one fermion on each site:
\[
|e'_2\rangle.
\]

**Common Traps**
- Forgetting that fermionic operator order matters.
- Writing the one-body term in the wrong order.
- Mixing up site inversion parity with singlet/triplet classification.
- Saying "triplet is odd" without saying odd under what.
- Forgetting that only opposite-spin double occupancy gets interaction energy U.
- Forgetting that strong repulsion still leads to a singlet ground state.

**Round 2**
Reply from memory in `04_answer_to_response_2.md`.

1. Write the ordered Fock-state convention used in the book and the sign picked up when the annihilation operator acts on an occupied orbital.
2. Write the general second-quantized forms of a one-body operator and a two-body operator for fermions.
3. Write the two-site Fermi-Hubbard Hamiltonian.
4. In the two-particle sector, which basis states are obviously eigenstates before any diagonalization, and what are their energies?
5. Write the odd-parity basis states
\[
|o'_1\rangle
\quad \text{and} \quad
|o'_2\rangle.
\]
Which one is a triplet? Which one gets interaction energy U?
6. Write the even-parity basis states
\[
|e'_1\rangle
\quad \text{and} \quad
|e'_2\rangle,
\]
and the 2 x 2 Hamiltonian matrix in that basis.
7. What is the approximate ground state for
\[
U \gg J > 0,
\]
and why is it not a triplet?
8. In one sentence each:
   a. Why do triplets avoid the contact interaction?
   b. Why is site inversion parity not the same thing as particle exchange?
9. State the particle-hole transformation for the two-site model and what particle sectors it relates.
10. Bonus: on a bipartite lattice, what operator changes the energy by plus or minus U and generates the pseudospin towers?
