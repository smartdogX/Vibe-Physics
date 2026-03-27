## Matsubara frequencies
Recall that the periodic condition $\psi(0)=\zeta\psi(\beta)$. 
What we can do is the Fourier transformation:
$$\psi(\tau)=\frac{1}{\sqrt{\beta}}\sum\psi_ne^{-\mathrm{i}\omega_n\tau}, \psi_n=\frac{1}{\sqrt{\beta}}\int_0^\beta\mathrm{d}\tau\psi(\tau)e^{\mathrm{i}\omega_n\tau}$$
where $\omega_n=\frac{2\pi n}{\beta}$ for bosons, and $\omega_n=\frac{2\pi(n+1)}{\beta}$ for fermions, they are known as **Matsubara frequencies**. 
To calculate the partition function, let's recall the formula:
$$\mathcal{Z}=\int D(\bar{\psi},\psi)e^{-S[\bar{\psi},\psi]}$$
$$S[\bar{\psi},\psi]=\int\mathrm{d}\tau [\bar{\psi}\partial_\tau\psi+H(\bar{\psi},\psi)-\mu N(\bar{\psi},\psi)]$$
Considering non-interacting gas, with the fourier transformation, the action can be written as 
$$S[\bar{\psi},\psi]=\sum_a\sum_{\omega_n}\bar{\psi}_{an}(-\mathrm{i}\omega_n+\epsilon_a-\mu)\psi_{an}$$
So now we can explicitly calculate the partition function,
$$\mathcal{Z_a}=\int D(\bar{\psi},\psi)e^{\sum_a\sum_{\omega_n}\bar{\psi}_{an}(-\mathrm{i}\omega_n+\epsilon_a-\mu)\psi_{an}}=\prod_n[\beta(-\mathrm{i}\omega_n+\epsilon_a-\mu)]^{-\zeta}$$
And the free energy
$$\mathcal{F}=-\frac{1}{\beta}\ln\mathcal{Z_a}=\frac{\zeta}{\beta}\sum_{n}\ln[\beta(-\mathrm{i}\omega_n+\epsilon_a-\mu)]$$
So the occupation number
$$n(\epsilon_a) = -\frac{\partial \mathcal{F}}{\partial\mu}=-\frac{\zeta}{\beta} \sum_n\frac{1}{\mathrm{i}\omega_n-(\epsilon_a-\mu)}$$
Then, the problem becomes how to calculate these series. If you don't care about the technical details, I can directly tell you the answer, that is $$n(\epsilon)=-\frac{\zeta}{\beta}\sum_n\frac{1}{\mathrm{i}\omega_n-(\epsilon-\mu)}=\frac{1}{\exp(\epsilon-\mu)-\zeta}$$For bosons, $n_B(\epsilon)=\frac{1}{\exp[\beta(\epsilon-\mu)]-1}$, and for fermions, $n_F(\epsilon)=\frac{1}{\exp[\beta(\epsilon-\mu)]+1}$.

If you do care about the details, let's go through the details: 
Generally speaking, considering a sum like
$$f(\omega_n)=\sum_nh(w_n)$$
where $\omega_n$ is **Matsubara frequencies**, try to think of this sum as the sum of the residue of a complex function, so that it can be calculated by the contour integral. For example, consider this function:
$$g(z)=\frac{\beta}{\exp(\beta z)-\zeta}$$
We immediately see that the strange point of this function is exactly $\mathrm{i}\omega_n$.
Now, choose $h(z)$ to be $\frac{\zeta}{\beta}\frac{1}{z-(\epsilon-\mu)}$, so
$$-\frac{\zeta}{\beta}\sum_n\frac{1}{\mathrm{i}\omega_n-(\epsilon-\mu)}=-\sum_n h(z)\Big|_{z=\mathrm{i}\omega_n}$$
Considering an infinite circle, the contour integral
$$\oint h(z)g(z)=\frac{1}{2\pi \mathrm{i}}\left[\sum_n h(z)\Big|_{z=\mathrm{i}\omega_n}+g(z)\Big|_{z=(\epsilon-\mu)}\right]=0$$
So,
$$-\frac{\zeta}{\beta}\sum_n\frac{1}{\mathrm{i}\omega_n-(\epsilon-\mu)}=-\sum_n h(z)\Big|_{z=\mathrm{i}\omega_n}=g(z)\Big|_{z=(\epsilon-\mu)}=\frac{1}{\exp(\epsilon-\mu)-\zeta}$$
Hence we derive Fermi-Dirac distribution and Bose-Einstein distribution, or non-interacting ideal gas distribution, i.e.