# Perturbation theory
We have defined the partition function before, as follows:
$$\mathcal{Z}=\int D(\bar{\psi},\psi)e^{-S[\bar{\psi},\psi]}$$
And expectation value of an operator can be written as 
$$\langle \hat{O}\rangle = \frac{\int D(\bar{\psi},\psi)\hat{O}e^{-S[\bar{\psi},\psi]} }{\int D(\bar{\psi},\psi)e^{-S[\bar{\psi},\psi]}}$$
This monster looks terrifying, how can we even deal with it?
So, guided by perturbation theory, let's start step by step. First, consider an original state, where 
$$\langle \hat{O}\rangle_0 = \frac{\int D(\bar{\psi},\psi)\hat{O}e^{-S_0[\bar{\psi},\psi]} }{\int D(\bar{\psi},\psi)e^{-S_0[\bar{\psi},\psi]}}$$
And then add some perturbation to the original state. Let's consider what will change.
$$\langle \hat{O}\rangle = \frac{\int D(\bar{\psi},\psi)\hat{O}e^{-S[\bar{\psi},\psi]} }{\int D(\bar{\psi},\psi)e^{-S[\bar{\psi},\psi]}}$$
What we need to do is that we need to learn how to calculate
$${\int D(\bar{\psi},\psi)e^{-S[\bar{\psi},\psi]}}$$
## $\phi^4$ theory
Let's start from the most simple case. What we can easily calculate is 
$$\int \mathrm{d}\phi e^{-\phi^2} = \sqrt{2\pi}$$
But when we try to calculate 
$$\int \mathrm{d}\phi e^{-\phi^2-g\phi^4}$$
We immediately find it is extremely hard to calculate(And mathematicians claim themselves smart!). Since g is small, let's do Taylor expansion:
$$\int \mathrm{d}\phi e^{-\phi^2-g\phi^4}=\sum_{n=0}^{\infty}\frac{(-g)^n}{n!}\int\mathrm{d}\phi e^{-\phi^2}\phi^{4n}=\sum_{n=0}^{\infty}(-g)^n\sqrt{2\pi}\frac{(4n-1)!!}{n!}\sim\left(\frac{-gn}{e}\right)^n$$
Strictly speaking, this is not even convergent!