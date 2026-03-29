# Green function in `\phi^4` theory

We have written the partition function in the form of a functional integral before,
$$
\mathcal{Z}=\int D\phi\,e^{-S[\phi]},
$$
and once we want to calculate some observable, what we really meet is
$$
\langle O[\phi]\rangle=\frac{\int D\phi\,O[\phi]e^{-S[\phi]}}{\int D\phi\,e^{-S[\phi]}}.
$$
This expression is compact, but it also hides the real difficulty: for an interacting theory, this integral is usually impossible to do exactly. The basic idea of Chapter 5 is that instead of attacking the full theory directly, we first find a solvable reference point and then study how interactions deform it. In other words, we write the action as a Gaussian part plus a perturbation and try to understand what changes order by order.

The simplest place to learn this logic is `\phi^4` theory,
$$
S[\phi]=\int d^dx\left[\frac12(\nabla\phi)^2+\frac r2\phi^2+g\phi^4\right].
$$
This model looks innocent, but it already contains the main ingredients of perturbation theory. The parameter `r` controls the mass scale or the distance from criticality, while `g` measures how strongly different fluctuations talk to each other. When `g=0`, the theory is Gaussian and can be calculated exactly. When `g` is small, we hope to expand around that Gaussian answer. Altland first reminds us that this expansion is not a convergent Taylor series in the strict mathematical sense. A one-dimensional toy integral,
$$
I(g)=\int dx\,e^{-x^2-gx^4},
$$
already shows the danger, because its perturbative coefficients grow like `(4n-1)!!`. So the series finally loses convergence due to combinatorial explosion. This is a very important warning: perturbation theory is usually asymptotic, but for weak coupling it can still be extremely useful.

The object that carries the most physical information is the correlation function. In general we define
$$
C_n(x_1,\cdots,x_n)=\langle\phi(x_1)\cdots\phi(x_n)\rangle,
$$
and the most important case is the two-point function
$$
G(x-x')=\langle\phi(x)\phi(x')\rangle.
$$
This is the Green function, also called the propagator. Physically, it tells us how a fluctuation created at one point is felt at another point. If the theory is translationally invariant, then the answer depends only on the difference `x-x'`. In the free theory the calculation is simple, because the quadratic action can be inverted directly:
$$
G_0(p)=\frac{1}{p^2+r}.
$$
This formula already tells us a lot. First, the Green function is literally the inverse of the quadratic operator. Second, after Fourier transforming back to real space, the correlation decays exponentially with a correlation length `\xi\sim r^{-1/2}`. So when `r\to 0`, the correlation length becomes very large, which is exactly the behavior we expect near a critical point. In this sense, the Green function is not just a formal symbol. It is a direct measurement of how correlated the field is.

Now let us see how interactions enter. We split the action into
$$
S[\phi]=S_0[\phi]+S_{\mathrm{int}}[\phi],\qquad S_{\mathrm{int}}[\phi]=g\int d^dx\,\phi^4(x),
$$
and then expand
$$
\langle O[\phi]\rangle=
\frac{\langle O[\phi]e^{-S_{\mathrm{int}}}\rangle_0}{\langle e^{-S_{\mathrm{int}}}\rangle_0}.
$$
Here `\langle\cdots\rangle_0` means the Gaussian average with respect to `S_0`. Once the theory is Gaussian, Wick's theorem becomes available, and that theorem is the engine behind the whole perturbative construction. It says that a higher-order Gaussian average can be reduced to a sum over pairwise contractions, and every contraction gives one free propagator `G_0`. This is exactly why the diagrammatic language works: a Feynman diagram is nothing but a picture of Wick contractions.

For the Green function, the first nontrivial correction comes from
$$
G(x,x')=
\frac{\left\langle \phi(x)\phi(x')\exp\left[-g\int d^dy\,\phi^4(y)\right]\right\rangle_0}
{\left\langle \exp\left[-g\int d^dy\,\phi^4(y)\right]\right\rangle_0}.
$$
Expanding to first order in `g`, we get
$$
G^{(1)}(x,x')=
-g\int d^dy\,\langle\phi(x)\phi^4(y)\phi(x')\rangle_0
+g\,\langle\phi(x)\phi(x')\rangle_0\int d^dy\,\langle\phi^4(y)\rangle_0.
$$
Now Wick's theorem can be used directly. The first Gaussian average contains six fields, so it breaks into all pairings. Altland shows that
$$
\langle\phi(x)\phi^4(y)\phi(x')\rangle_0
=3G_0(x-x')G_0(0)^2+12G_0(x-y)G_0(0)G_0(y-x').
$$
The second term from the denominator gives exactly the same vacuum-bubble contribution,
$$
\langle\phi(x)\phi(x')\rangle_0\langle\phi^4(y)\rangle_0
=3G_0(x-x')G_0(0)^2.
$$
So the disconnected piece cancels, and what survives is
$$
G^{(1)}(x,x')=-12g\int d^dy\,G_0(x-y)G_0(0)G_0(y-x').
$$
This example is very instructive. It shows that the denominator of the expectation value is not an annoying extra factor: it removes vacuum graphs and leaves only connected contributions. It also shows where the first ultraviolet problem comes from, because
$$
G_0(0)=\int\frac{d^dp}{(2\pi)^d}\frac{1}{p^2+r}
$$
is divergent at large momentum in sufficiently high dimension. At the same time, when `r\to 0`, infrared singular behavior appears because long-wavelength fluctuations become too strong. So already at low order the Green function teaches us both the power and the limits of perturbation theory.

At this point the diagrammatic rules almost explain themselves. Every external field `\phi(x)` is drawn as an external point with one leg. Every factor `\phi^4(y)` is drawn as a vertex with four legs. Whenever two field variables are contracted, we replace that pair by one line carrying the free propagator `G_0`. Internal coordinates such as `y` are integrated over, and if we work at order `n` in the expansion we attach the factor `(-g)^n/n!`. Because Altland writes the interaction as `g\phi^4` rather than `g\phi^4/4!`, the symmetry and combinatorial factors have to be counted explicitly instead of being hidden in the definition of the coupling. In momentum space the picture becomes even cleaner: every internal line contributes
$$
G_0(p)=\frac{1}{p^2+r},
$$
and every vertex satisfies momentum conservation, so for a `\phi^4` vertex we must have
$$
p_1+p_2+p_3+p_4=0.
$$
The number of independent internal momentum integrals is then exactly the loop number of the diagram. This is the practical reason why momentum space is so useful.

The real conceptual step of the chapter is that one should not think of the Green function as an endless pile of separate diagrams. Instead, one reorganizes the expansion by collecting all one-particle-irreducible insertions into the self-energy `\Sigma`. Then the full propagator satisfies Dyson's equation
$$
G=G_0+G_0\Sigma G,
$$
or, equivalently,
$$
G^{-1}=G_0^{-1}-\Sigma.
$$
This equation is simple, but it changes the way we think. The bare Green function `G_0` describes free propagation, while `\Sigma` measures how interactions dress that propagation. So the practical goal is no longer to stare at every diagram separately, but to understand which classes of diagrams really renormalize the propagator in an essential way.

My own understanding of this chapter is that Green functions are the center of the whole discussion. In the free theory, `G_0` tells us the length scale of correlations. In the interacting theory, every scattering process modifies that answer, and the modification can be written as diagrammatic corrections. Wick's theorem gives the algebraic rule, Feynman diagrams give the visual language, and Dyson's equation gives the final structure. So Chapter 5 is really teaching us how to move from a formal functional integral to a physically readable description of propagation, fluctuation, and interaction.
