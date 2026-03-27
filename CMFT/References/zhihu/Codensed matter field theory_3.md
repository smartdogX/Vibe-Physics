## Functional field theory
Now we consider how to calculate the partition function
$$\mathcal{Z}=\sum_n\langle n|e^{-\beta (\hat{H}-\mu\hat{N})}|n\rangle$$
Notice that the form is actually very similar to the Feymann path integral, as a result, by inserting the indentical operator 
$$\hat{I}=\int\frac{\mathrm{d}\psi \mathrm{d}\psi^\dagger}{\pi^{\frac{1+\zeta}{2}}}\exp(-|\psi|^2)|\psi\rangle\langle\psi|=\int\mathrm{d}(\bar{\psi},\psi)e^{-\psi^{\dagger}\psi}|\psi\rangle\langle\psi|$$
Using the same idea as the Feymann path integral, we can actually calculate the partition function explicitly: 
$$\mathcal{Z}=\int\mathrm{d}(\bar{\psi},\psi)e^{-\psi^\dagger\psi}\sum_n\langle n|\psi\rangle\langle\psi|e^{-\beta(\hat{H}-\mu\hat{N})}|n\rangle$$
With $$\langle n|\psi\rangle\langle\psi|n\rangle=\langle\zeta\psi|n\rangle\langle n|\psi\rangle$$
We get
$$\mathcal{Z}=\int\mathrm{d}(\bar{\psi},\psi)e^{-\psi^\dagger\psi}\sum_n\langle\zeta\psi|e^{-\beta(\hat{H}-\mu\hat{N})}|n\rangle\langle n|\psi\rangle=\int\mathrm{d}(\bar{\psi},\psi)e^{-\psi^\dagger\psi}\langle\zeta\psi|e^{-\beta(\hat{H}-\mu\hat{N})}|\psi\rangle$$
Divide the $\beta$ as intervals with length $\delta=\frac{\beta}{N}$, perform the trick again
$$\mathcal{Z}=\int\mathrm{d}(\bar{\psi},\psi)e^{-\psi^\dagger\psi}\langle\zeta\psi|e^{-\beta(\hat{H}-\mu\hat{N})}|\psi\rangle=\int\mathrm{d}(\bar{\psi},\psi)e^{-\psi^\dagger\psi}\langle\zeta\psi|e^{-\delta(\hat{H}-\mu\hat{N})}\int\mathrm{d}(\bar{\psi_1},\psi_1)e^{-\psi_1^{\dagger}\psi_1}|\psi_1\rangle\langle\psi_1|e^{-\delta(\hat{H}-\mu\hat{N})}|\int\mathrm{d}(\bar{\psi_2},\psi_2)e^{-\psi_2^{\dagger}\psi_2}|\psi_2\rangle\langle\psi_2|e^{-\delta(\hat{H}-\mu\hat{N})}\cdots|\psi\rangle$$
With$$\langle\psi_{j}|e^{-\delta(\hat{H}-\mu\hat{N})}|\psi_{j+1}\rangle=e^{\bar{\psi}_j\psi_{j+1}-\delta(\hat{H(\bar{\psi},\psi)}-\mu\hat{N(\bar{\psi},\psi)})}$$Finally we can get this form,
$$\mathcal{Z}=\int_{\psi^0=\zeta\psi^{N}}\prod_{n=1}^{N}\mathrm{d}(\bar{\psi}^n,\psi^n)e^{-\delta\sum_{n=0}^{N-1}[\delta^{-1}(\bar{\psi}^n-\bar{\psi}^{n+1})\psi^n+H(\bar{\psi}^{n+1},\psi^n)-\mu N(\bar{\psi}^{n+1},\psi^n)]}$$
the discrete Euclidean-time action$$S=\delta\sum_{n=0}^{N-1}[\delta^{-1}(\bar{\psi}^n-\bar{\psi}^{n+1})\psi^n+H(\bar{\psi}^{n+1},\psi^n)-\mu N(\bar{\psi}^{n+1},\psi^n)]$$Go to continuum limit, we get
$$\mathcal{Z}=\int D(\bar{\psi},\psi)e^{-S[\bar{\psi},\psi]}$$
and
$$S[\bar{\psi},\psi]=\int\mathrm{d}\tau [\bar{\psi}\partial_\tau\psi+H(\bar{\psi},\psi)-\mu N(\bar{\psi},\psi)]$$
With the periodic condition $\psi(0)=\zeta\psi(\beta)$.
Now we can see the purpose of define the coherent state, which is the eigenstate of the creation and annihilation operator, in this way, we can seperate the whole integral by making infinisemial change, and it is also a convinient way to express Hamiltonian.
Path integral is more than just a formula, it is actually a way of thinking, by using the idea of path integral, we build the foundation of the quantum field theory.