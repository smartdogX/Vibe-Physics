# QM2 Midterm Formula Sheet

Based on `textbook.pdf` Chapters 12-13 and the review notes in this folder. This is a high-yield sheet for fast recall, not a full set of derivations.

## 1. Bosons: second quantization core

**Bosonic Fock states**
\[
|n_1,n_2,\dots,n_k,\dots\rangle
\]
\[
\hat a_k |n_1,\dots,n_k,\dots\rangle
=\sqrt{n_k}\,|n_1,\dots,n_k-1,\dots\rangle
\]
\[
\hat a_k^\dagger |n_1,\dots,n_k-1,\dots\rangle
=\sqrt{n_k}\,|n_1,\dots,n_k,\dots\rangle
\]
\[
\hat a_k |0\rangle = 0,
\qquad
\hat n_k \equiv \hat a_k^\dagger \hat a_k
\]

**Bosonic algebra**
\[
[\hat a_k,\hat a_l]=0,
\qquad
[\hat a_k^\dagger,\hat a_l^\dagger]=0,
\qquad
[\hat a_k,\hat a_l^\dagger]=\delta_{kl}
\]

**One-body operator**
\[
\hat O_{1b}=\sum_{k,l} o_{kl}\hat a_k^\dagger \hat a_l
\]

**Two-body operator**
\[
\hat O_{2b}=\frac12\sum_{k,l,r,s} o_{klsr}\hat a_k^\dagger \hat a_l^\dagger \hat a_r \hat a_s
\]

**Density-density interaction**
\[
\hat V_{\rm int}
=\frac12\sum_{k,l} v_{kl} :\hat n_k \hat n_l:
=\frac12\sum_{k,l} v_{kl}\hat a_k^\dagger \hat a_l^\dagger \hat a_l \hat a_k
\]

**Two-boson matrix element**
\[
\langle pq|\hat O_{2b}|pq\rangle_{\rm boson}
=o_{pqpq}+o_{pqqp}
\]
Direct and exchange terms add for bosons.

## 2. Two-site Bose-Hubbard model

**Hamiltonian**
\[
\hat H_{2BH}
=-J(\hat a_L^\dagger \hat a_R+\hat a_R^\dagger \hat a_L)
+\frac U2\left[\hat n_L(\hat n_L-1)+\hat n_R(\hat n_R-1)\right]
\]

**Two-boson basis**
\[
|0,2\rangle,\qquad |1,1\rangle,\qquad |2,0\rangle
\]

**Parity basis**
\[
|e_1\rangle=\frac{|0,2\rangle+|2,0\rangle}{\sqrt2},
\qquad
|e_2\rangle=|1,1\rangle,
\qquad
|o_1\rangle=\frac{|0,2\rangle-|2,0\rangle}{\sqrt2}
\]

**Odd state**
\[
\hat H_{2BH}|o_1\rangle = U|o_1\rangle
\]

**Even block**
\[
H_{\rm even}
=\begin{pmatrix}
U & -2J \\
-2J & 0
\end{pmatrix}
\]

**Eigenenergies**
\[
E_o=U,
\qquad
E_\pm=\frac U2 \pm \frac12\sqrt{U^2+16J^2}
\]

**Eigenstates**
\[
|\psi_-\rangle=\sin\frac{\vartheta}{2}|e_1\rangle+\cos\frac{\vartheta}{2}|e_2\rangle,
\qquad
|\psi_+\rangle=\cos\frac{\vartheta}{2}|e_1\rangle-\sin\frac{\vartheta}{2}|e_2\rangle
\]
\[
\tan\vartheta=\frac{4J}{U}
\]

**Important limits**
\[
U \gg J>0
\quad \Rightarrow \quad
|\psi_-\rangle \approx |1,1\rangle
\]
\[
U \ll -J
\quad \Rightarrow \quad
|\psi_-\rangle \approx \frac{|0,2\rangle+|2,0\rangle}{\sqrt2}
\]

## 3. Bose-Hubbard spin and number-phase language

**Schwinger spin mapping for two modes**
\[
\hat S_x=\frac12(\hat a_L^\dagger \hat a_R+\hat a_R^\dagger \hat a_L)
\]
\[
\hat S_y=\frac1{2i}(\hat a_L^\dagger \hat a_R-\hat a_R^\dagger \hat a_L)
\]
\[
\hat S_z=\frac12(\hat n_L-\hat n_R),
\qquad
\hat N=\hat n_L+\hat n_R
\]

**Two-site Bose-Hubbard in spin form**
\[
\hat H_{2BH}
=-2J\hat S_x+U\hat S_z^2+\frac U4(\hat N^2-2\hat N)
\]
For fixed `N`, the last term is a constant shift.

**Spin value for fixed boson number**
\[
S=\frac N2
\]
For `N=2`, the three states `|2,0>`, `|1,1>`, `|0,2>` form a spin-1 multiplet.

**Relative number and phase**
\[
\hat N=\hat n_R+\hat n_L,
\qquad
\hat n=\frac{\hat n_R-\hat n_L}{2}
\]
\[
\hat n=-\hat S_z
\]
\[
[\hat n,\hat \phi]=i
\]

**Exact number-phase form**
\[
\hat H_{2BH}
=-J\left(
\sqrt{\frac{\hat N}{2}-\hat n}\,e^{i\hat\phi}\sqrt{\frac{\hat N}{2}+\hat n}
+
\sqrt{\frac{\hat N}{2}+\hat n}\,e^{-i\hat\phi}\sqrt{\frac{\hat N}{2}-\hat n}
\right)
+U\hat n^2+\frac U4(\hat N^2-2\hat N)
\]

**Large-`N` quantum rotor approximation**
\[
\hat H_{2QR}=-JN\cos\hat\phi + U\hat n^2
\]

**Phase-representation Schr. equation**
\[
-U\frac{d^2\psi(\phi)}{d\phi^2}-JN\cos\phi\,\psi(\phi)=E\psi(\phi)
\]

**Classical Josephson / rotor equations**
\[
\frac{dn}{dt}=JN\sin\phi,
\qquad
\frac{d\phi}{dt}=-2Un
\]

## 4. Many-site Bose-Hubbard and mean-field limit

**Bose-Hubbard Hamiltonian**
\[
\hat H_{BH}
=-J\sum_{j=1}^{L}\left(\hat a_j^\dagger \hat a_{j+1}+\hat a_{j+1}^\dagger \hat a_j\right)
+\frac U2\sum_{j=1}^{L}\hat n_j(\hat n_j-1)
\]

**Discrete Gross-Pitaevskii / discrete nonlinear Schrodinger equation**
\[
i\hbar \frac{d\psi_j}{dt}
=-J(\psi_{j+1}-2\psi_j+\psi_{j-1})+U|\psi_j|^2\psi_j
\]

**Continuum nonlinear Schrodinger equation**
\[
i\hbar\frac{\partial \psi(x,t)}{\partial t}
=-\frac{\hbar^2}{2m_{\rm eff}}\frac{\partial^2\psi(x,t)}{\partial x^2}
+g|\psi(x,t)|^2\psi(x,t)
\]
\[
m_{\rm eff}=\frac{\hbar^2}{2Ja^2},
\qquad
g=Ua
\]

## 5. Fermions: second quantization core

**Fermionic algebra**
\[
\{\hat c_k,\hat c_l^\dagger\}=\delta_{kl},
\qquad
\{\hat c_k,\hat c_l\}=0,
\qquad
\{\hat c_k^\dagger,\hat c_l^\dagger\}=0
\]

**Ordered fermionic Fock states**
\[
|n_1,n_2,\dots,n_k,\dots\rangle
=(\hat c_1^\dagger)^{n_1}(\hat c_2^\dagger)^{n_2}\cdots(\hat c_k^\dagger)^{n_k}\cdots|0\rangle
\]
\[
n_k \in \{0,1\}
\]

**Action with sign**
\[
\hat c_k|n_1,\dots,n_k=1,\dots\rangle
=(-1)^{\sum_{j<k} n_j}|n_1,\dots,n_k=0,\dots\rangle
\]
\[
\hat c_k^\dagger|n_1,\dots,n_k=0,\dots\rangle
=(-1)^{\sum_{j<k} n_j}|n_1,\dots,n_k=1,\dots\rangle
\]

**One-body operator**
\[
\hat O_{1b}=\sum_{k,l} o_{kl}\hat c_k^\dagger \hat c_l
\]

**Two-body operator**
\[
\hat O_{2b}
=\frac12\sum_{k,l,r,s} o_{klsr}\hat c_k^\dagger \hat c_l^\dagger \hat c_r \hat c_s
\]

**Density-density interaction**
$$
\hat V_{\rm int}
=\frac12\sum_{k,l}v_{kl}:\hat n_k\hat n_l:
=\frac12\sum_{k,l}v_{kl}\hat c_k^\dagger \hat c_l^\dagger \hat c_l \hat c_k
$$

**Two-fermion matrix element**
\[
\langle pq|\hat O_{2b}|pq\rangle_{\rm fermion}
=o_{pqpq}-o_{pqqp}
\]
Direct minus exchange for fermions.

## 6. Two-site Fermi-Hubbard model

**Hamiltonian**
\[
\hat H_{2FH}
=-J\sum_{\sigma=\uparrow,\downarrow}
\left(
\hat c_{L\sigma}^\dagger \hat c_{R\sigma}
+\hat c_{R\sigma}^\dagger \hat c_{L\sigma}
\right)
+U(\hat n_{L\uparrow}\hat n_{L\downarrow}+\hat n_{R\uparrow}\hat n_{R\downarrow})
\]

**Two obvious eigenstates**
\[
|\uparrow,\uparrow\rangle,
\qquad
|\downarrow,\downarrow\rangle
\]
Both have energy `0`.

**Odd-parity states**
\[
|o_1'\rangle
=\frac{|0,\uparrow\downarrow\rangle-|\uparrow\downarrow,0\rangle}{\sqrt2}
\]
\[
|o_2'\rangle
=\frac{|\uparrow,\downarrow\rangle+|\downarrow,\uparrow\rangle}{\sqrt2}
\]
\[
|o_1'\rangle: E=U,
\qquad
|o_2'\rangle: E=0
\]
\[
|o_2'\rangle = |t_0\rangle
\]

**Even-parity states**
\[
|e_1'\rangle
=\frac{|0,\uparrow\downarrow\rangle+|\uparrow\downarrow,0\rangle}{\sqrt2}
\]
\[
|e_2'\rangle
=\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}
\]
\[
|e_2'\rangle = |s\rangle
\]

**Even block**
\[
H_{\rm even}
=\begin{pmatrix}
U & -2J \\
-2J & 0
\end{pmatrix}
\]
Same matrix and same eigenvalues as the two-boson even sector.

**Key limits**
\[
U \gg J>0
\quad \Rightarrow \quad
|{\rm gs}\rangle \approx |e_2'\rangle
=\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}
\]
\[
U \ll -J
\quad \Rightarrow \quad
|{\rm gs}\rangle \approx |e_1'\rangle
=\frac{|0,\uparrow\downarrow\rangle+|\uparrow\downarrow,0\rangle}{\sqrt2}
\]

**Triplet and singlet**
\[
|t_{+1}\rangle=|\uparrow,\uparrow\rangle,
\qquad
|t_{0}\rangle=\frac{|\uparrow,\downarrow\rangle+|\downarrow,\uparrow\rangle}{\sqrt2},
\qquad
|t_{-1}\rangle=|\downarrow,\downarrow\rangle
\]
\[
|s\rangle=\frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}
\]
Triplets avoid the contact interaction because the spatial/orbital part is antisymmetric, so the coincidence amplitude vanishes.

## 7. Fermi-Hubbard model: many-site form and symmetries

**Many-site Hamiltonian**
\[
\hat H_{FH}
=-J\sum_{\langle i,j\rangle}\sum_{\sigma=\uparrow,\downarrow}
\left(
\hat c_{i\sigma}^\dagger \hat c_{j\sigma}
+\hat c_{j\sigma}^\dagger \hat c_{i\sigma}
\right)
+U\sum_i \hat n_{i\uparrow}\hat n_{i\downarrow}
\]

**Particle-number operators**
\[
\hat N=\hat N_\uparrow+\hat N_\downarrow,
\qquad
\hat N_\sigma=\sum_i \hat n_{i\sigma}
\]
\[
[\hat H_{FH},\hat N_\sigma]=0,
\qquad
[\hat H_{FH},\hat N]=0
\]

**Local spin operator**
\[
\hat s_i^\alpha
=\frac12\sum_{m,n=\uparrow,\downarrow}\hat c_{im}^\dagger(\sigma^\alpha)_{mn}\hat c_{in}
\]

**Explicit local spin components**
\[
\hat s_i^x=\frac12\left(\hat c_{i\downarrow}^\dagger \hat c_{i\uparrow}+\hat c_{i\uparrow}^\dagger \hat c_{i\downarrow}\right)
\]
\[
\hat s_i^y=\frac{i}{2}\left(\hat c_{i\downarrow}^\dagger \hat c_{i\uparrow}-\hat c_{i\uparrow}^\dagger \hat c_{i\downarrow}\right)
\]
\[
\hat s_i^z=\frac12\left(\hat n_{i\uparrow}-\hat n_{i\downarrow}\right)
\]

**Total spin**
\[
\hat S_z=\frac12(\hat N_\uparrow-\hat N_\downarrow)
\]
\[
\hat S_+=\sum_i \hat c_{i\uparrow}^\dagger \hat c_{i\downarrow},
\qquad
\hat S_-=\sum_i \hat c_{i\downarrow}^\dagger \hat c_{i\uparrow}
\]
\[
[\hat S_+,\hat S_-]=2\hat S_z,
\qquad
[\hat S_z,\hat S_\pm]=\pm \hat S_\pm
\]
\[
\hat S^2=\frac12(\hat S_+\hat S_-+\hat S_-\hat S_+)+\hat S_z^2
\]
\[
[\hat H_{FH},\hat S_z]=[\hat H_{FH},\hat S_+]=[\hat H_{FH},\hat S_-]=[\hat H_{FH},\hat S^2]=0
\]

## 8. Pseudospin, particle-hole symmetry, and half filling

**Local pseudospin operators**
\[
\hat\gamma_{iz}=\frac12(\hat n_{i\uparrow}+\hat n_{i\downarrow}-1)
\]
\[
\hat\gamma_{i+}=\hat c_{i\uparrow}^\dagger \hat c_{i\downarrow}^\dagger,
\qquad
\hat\gamma_{i-}=\hat c_{i\downarrow}\hat c_{i\uparrow}
\]

**Bipartite-lattice pseudospin**
\[
\hat\Upsilon_z=\sum_i \hat\gamma_{iz}=\frac12(\hat N-V)
\]
\[
\hat\Upsilon_+=\sum_i \eta_i \hat\gamma_{i+},
\qquad
\hat\Upsilon_-=\sum_i \eta_i \hat\gamma_{i-}
\]
\[
\eta_i=
\begin{cases}
+1, & i\in A \\
-1, & i\in B
\end{cases}
\]
\[
[\hat\Upsilon_+,\hat\Upsilon_-]=2\hat\Upsilon_z,
\qquad
[\hat\Upsilon_z,\hat\Upsilon_\pm]=\pm \hat\Upsilon_\pm
\]
\[
[\hat H_{FH},\hat\Upsilon_\pm]=\pm U\hat\Upsilon_\pm
\]
So `\hat\Upsilon_\pm` generate pseudospin towers with energy shifts `\pm U`.

**Real spin vs pseudospin**
\[
\hat S_+ = \sum_i \hat c_{i\uparrow}^\dagger \hat c_{i\downarrow}
\quad \text{flips spin}
\]
\[
\hat\Upsilon_+ = \sum_i \eta_i \hat c_{i\uparrow}^\dagger \hat c_{i\downarrow}^\dagger
\quad \text{creates a pair}
\]

**Two-site particle-hole transformation**
\[
\hat d_{L\sigma}^\dagger=\hat c_{L\sigma},
\qquad
\hat d_{L\sigma}=\hat c_{L\sigma}^\dagger
\]
\[
\hat d_{R\sigma}^\dagger=-\hat c_{R\sigma},
\qquad
\hat d_{R\sigma}=-\hat c_{R\sigma}^\dagger
\]

**Bipartite-lattice particle-hole transformation**
\[
\hat d_{i\sigma}^\dagger=\eta_i \hat c_{i\sigma},
\qquad
\hat d_{i\sigma}=\eta_i \hat c_{i\sigma}^\dagger
\]

**Implementation used in the notes**
\[
\hat U_{\rm ph}=\prod_{i,\sigma}\left(\hat c_{i\sigma}+\eta_i \hat c_{i\sigma}^\dagger\right)
\]

**Occupation mapping**
\[
\hat n_{i\sigma}\rightarrow 1-\hat n_{i\sigma}
\]

**Energy relation**
\[
E_\alpha(V,N_\uparrow,N_\downarrow)
=E_\alpha(V,V-N_\uparrow,V-N_\downarrow)
+U(N_\uparrow+N_\downarrow-V)
\]

**Sector mapping**
\[
0 \leftrightarrow 4,\qquad 1 \leftrightarrow 3,\qquad 2 \leftrightarrow 2
\]
for the two-site model.

**Half filling**
\[
N_\uparrow=N_\downarrow=\frac V2
\]
At half filling the model maps back to itself under particle-hole symmetry.

## 9. Hard-core bosons, spin mapping, and Jordan-Wigner

**Hard-core boson constraints**
\[
\hat b_j^\dagger \hat b_j+\hat b_j \hat b_j^\dagger = 1,
\qquad
(\hat b_j^\dagger)^2=(\hat b_j)^2=0
\]

**Map hard-core bosons to spin-1/2**
\[
\hat b_j^\dagger \leftrightarrow \sigma_j^+,
\qquad
\hat b_j \leftrightarrow \sigma_j^-,
\qquad
\hat n_j=\frac{\sigma_j^z+1}{2}
\]

**Hard-core boson Hamiltonian**
\[
\hat H_{HCB}
=-J\sum_j(\hat b_j^\dagger \hat b_{j+1}+\hat b_{j+1}^\dagger \hat b_j)
\]

**XX model**
\[
\hat H_{XX}
=-J\sum_j(\sigma_j^+\sigma_{j+1}^-+\sigma_{j+1}^+\sigma_j^-)
=-\frac J2\sum_j(\sigma_j^x\sigma_{j+1}^x+\sigma_j^y\sigma_{j+1}^y)
\]

**Jordan-Wigner transformation for spinless fermions in 1D**
\[
\hat c_j^\dagger
=\exp\left(i\pi\sum_{l=1}^{j-1}\sigma_l^+\sigma_l^-\right)\sigma_j^+
\]
\[
\hat c_j
=\exp\left(-i\pi\sum_{l=1}^{j-1}\sigma_l^+\sigma_l^-\right)\sigma_j^-
\]
\[
\hat n_j=\hat c_j^\dagger \hat c_j=\sigma_j^+\sigma_j^-=\frac{\sigma_j^z+1}{2}
\]

## 10. Fast exam traps

- One-body operator order is always `create then destroy`:
\[
\sum_{kl} o_{kl}\hat a_k^\dagger \hat a_l,
\qquad
\sum_{kl} o_{kl}\hat c_k^\dagger \hat c_l
\]
- Bosons:
\[
\frac U2\,\hat n(\hat n-1)
\]
on a site.
- Fermions:
\[
U\,\hat n_\uparrow \hat n_\downarrow
\]
on a site.
- Bosons: exchange term enters with `+`.
- Fermions: exchange term enters with `-`.
- Bose-Hubbard `\hat S_z` means left-right number imbalance.
- Fermi-Hubbard `\hat S_z` means up-down spin imbalance.
- Do not confuse site inversion `L <-> R` with particle exchange `1 <-> 2`.
- Do not confuse `\hat S_+` with `\hat\Upsilon_+`.
- For repulsive two-site Fermi-Hubbard:
\[
|{\rm gs}\rangle \approx \frac{|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle}{\sqrt2}
\]
not the triplet.
