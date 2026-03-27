## Coherent state
When we start to talk about quantum statistic mechanics, it is convinient for us to use the second quantization. So basically second quantization is nothing but consider a quantum system in "particle number" representation. In this way, although it seems that we lost some information comparing to the position or momentum representation. However, it makes the statistics much easier for us. Now, let's consider a boson system, since we use the creation and annihilation operators to discribe the quantum system. It's convinent for us to find the eigenstate of these operators. It's actually very easy, just try this state:
$$|\psi_i\rangle=\exp\left(\psi_ia^{\dagger}_i\right)|0\rangle=\left(1+(\psi_ia^{\dagger}_i)+\frac{1}{2}(\psi_ia^{\dagger}_i)^2+\cdots\right)|0\rangle=\sum_{n}\frac{\psi_i^n}{\sqrt{n!}}|n\rangle$$
Here we use $\left(a^{\dagger}\right)^n|0\rangle=\sqrt{n!}|n\rangle$. And This state is the eigenstate of the operators $a_i$. With $a_i\left(a_i^{\dagger}\right)^n=na_i\left(a_i^{\dagger}\right)^{n-1}$The provement is also straightforward: 
$$a_i|\psi_i\rangle=a_i\left(1+(\psi_ia^{\dagger}_i)+\frac{1}{2}(\psi_ia^{\dagger}_i)^2+\cdots\right)|0\rangle=\psi_i\left(1+(\psi_ia^{\dagger}_i)+\frac{1}{2}(\psi_ia^{\dagger}_i)^2+\cdots\right)|0\rangle=\psi_i|\psi\rangle$$
We have
$$\langle\psi_i|\psi_i\rangle=\exp\left(\psi^*_i\psi_i\right)$$
We can normalize the state as $\exp\left(-\frac{1}{2}|\psi_i|^2\right)|\psi_i\rangle$. Also, let's consider the identical operator in this representation. We know that
$$\hat{I}=\sum_n|n\rangle\langle n|$$
And
$$|\psi_i\rangle\langle\psi_i|=\left(\sum_{n}\frac{\psi_i^n}{\sqrt{n!}}|n\rangle\right)\left(\langle m|\sum_{m}\frac{\left(\psi^*_i\right)^{m}}{\sqrt{m!}}\right)=\sum_{n,m}\frac{\psi_i^n\left(\psi^*_i\right)^{m}}{\sqrt{n!m!}}|n\rangle\langle m|$$
With
$$\int\frac{\mathrm{d}\psi_i\mathrm{d}\psi^*_i}{\pi}\sum_{n,m}\exp(-|\psi_i|^2)\frac{\psi_i^n\left(\psi^*_i\right)^{m}}{\sqrt{n!m!}}=n!\delta_{nm}$$
We have
$$\hat{I}=\int\frac{\mathrm{d}\psi_i\mathrm{d}\psi^*_i}{\pi}\exp(-|\psi_i|^2)|\psi_i\rangle\langle\psi_i|$$
If we have many different operators, say $a_i (i=1,2,3\cdots)$, we just get a state which is the direct product of states of different. And we just generalize everything. The state is like
$$|\psi\rangle=\exp\left(\sum_i\psi_ia^{\dagger}_i\right)|0\rangle$$
Define a vector $$\psi=\begin{pmatrix}\psi_1\\ \psi_2\\\vdots\end{pmatrix}$$Now identical operator becomes  
$$\hat{I}=\int\frac{\mathrm{d}\psi \mathrm{d}\psi^\dagger}{\pi}\exp(-|\psi|^2)|\psi\rangle\langle\psi|$$
For fermion system, things will become slightly different because the fermion operators satisfy the anti-commute relation: 
$$\{a^{\dagger}_i,a^{\dagger}_j\}=a^{\dagger}_ia^{\dagger}_j+a^{\dagger}_ja^{\dagger}_i=0$$
If we still want to keep the form of coherent state unchanged, we need to introduce Grassmann algebra. Say,
$$a_i|\eta\rangle=\eta_i|\eta\rangle$$
$$|\eta\rangle=\exp\left(-\sum_i\eta_ia_i^{\dagger}|0\rangle\right)$$
Here $\eta_i$ is not number, but a new algebra structure. If we define: 
$$\{\eta_i,\eta_j\}=\eta_i\eta_j+\eta_j\eta_i=0$$
$$\int\mathrm{d}\eta_i\eta_i=1$$
$$\int\mathrm{d}\eta_i=0$$
$$\partial_{\eta_i}\eta_j=\delta_{ij}$$
Everything will remain nearly unchanged. 
We can express the coherent of boson system and fermion system in an elegant way
$$|\psi\rangle=\exp\left(\zeta\sum_i\psi_ia_i^{\dagger}\right)$$
$$\hat{I}=\int\frac{\mathrm{d}\psi \mathrm{d}\psi^\dagger}{\pi^{\frac{1+\zeta}{2}}}\exp(-|\psi|^2)|\psi\rangle\langle\psi|$$
$\zeta$ is 0 for bosons and 1 for fermions.
## Functional path integral
Recall how we represent the partition function in the form of path integral: 
Start with
$$Z=\sum_{n}\langle n|e^{-\beta\left(\hat{H}-\mu\hat{N}\right)}|n\rangle$$