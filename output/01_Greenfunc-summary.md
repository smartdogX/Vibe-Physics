# Green Function Summary

Based on Chapter 5 of Altland and Simons, this note focuses on the role of the Green function in perturbation theory, with emphasis on `\phi^4` theory and the basic logic of Feynman diagrams.

## 1. Main idea of the chapter

Chapter 5 explains how to study an interacting many-body system when we already understand a simpler reference theory. The strategy is:

1. Split the action into a solvable Gaussian part `S_0` and an interaction part `S_{\mathrm{int}}`.
2. Expand observables in powers of the interaction strength.
3. Evaluate the Gaussian averages by Wick's theorem.
4. Organize the huge number of terms graphically by Feynman diagrams.

Altland first warns that perturbation theory is usually **asymptotic**, not truly convergent. The toy integral

```math
I(g)=\int dx\, e^{-x^2-gx^4}
```

already shows the problem: the number of pairings grows factorially, so the series eventually diverges. The lesson is important: perturbation theory is useful at weak coupling, but it is not a mathematically convergent Taylor series in general.

## 2. `\phi^4` theory as the prototype

The chapter uses the scalar field model

```math
Z=\int D\phi\, e^{-S[\phi]}, \qquad
S[\phi]=\int d^d x \left[\frac12 (\nabla \phi)^2+\frac r2 \phi^2+g\phi^4\right].
```

This is the simplest interacting field theory that still contains all the essential perturbative structures.

My understanding of the parameters is:

- `r` sets the distance from criticality.
- `g` is the interaction strength.
- The Gaussian part tells us how fluctuations propagate when interactions are absent.
- The `\phi^4` term makes different fluctuations scatter off each other.

This model is not just a toy. Near a second-order phase transition, many systems with a single scalar order parameter reduce to this Ginzburg-Landau form.

## 3. What the Green function means

The chapter defines the `n`-point correlation functions as

```math
C_n(x_1,\dots,x_n)=\langle \phi(x_1)\cdots \phi(x_n)\rangle.
```

The central object is the two-point function

```math
G(x_1-x_2)=\langle \phi(x_1)\phi(x_2)\rangle,
```

also called the propagator or Green function.

This quantity measures how strongly a fluctuation at one point is correlated with a fluctuation at another point. In translationally invariant systems it depends only on the difference `x_1-x_2`.

For the free theory (`g=0`),

```math
G_0(p)=\frac{1}{p^2+r}.
```

This formula is extremely important. It shows that:

- the Green function is the inverse of the quadratic operator in the action;
- in real space, correlations decay exponentially with correlation length

```math
\xi \sim r^{-1/2};
```

- when `r \to 0`, the correlation length diverges, signaling critical behavior.

So the Green function is not just a formal object. It directly tells us the spatial range and strength of fluctuations.

## 4. How perturbation theory enters

Write

```math
S[\phi]=S_0[\phi]+S_{\mathrm{int}}[\phi], \qquad
S_{\mathrm{int}}=g\int d^d x\, \phi^4(x).
```

Then expand expectation values in powers of `g`:

```math
\langle X[\phi]\rangle
=
\frac{\langle X[\phi] e^{-S_{\mathrm{int}}}\rangle_0}{\langle e^{-S_{\mathrm{int}}}\rangle_0}.
```

Now every term becomes a Gaussian average, and Gaussian averages are evaluated by **Wick's theorem**. That means every higher-order average is reduced to sums of pairwise contractions, and each contraction gives one free propagator `G_0`.

This is the real origin of diagrams: a Feynman diagram is a compact picture of all those Wick contractions.

## 5. Basic rules for plotting Feynman diagrams in this chapter

For Altland's `\phi^4` theory, the basic diagrammatic rules are:

1. Each external field `\phi(x)` is drawn as an external vertex with one leg.
2. Each interaction term `\phi^4(y)` is drawn as one internal vertex with four legs.
3. Each pair contraction contributes one free Green function:

```math
\phi(x)\phi(y)\;\longrightarrow\; G_0(x-y)
```

4. Internal coordinates such as `y` are integrated over.
5. At order `n`, the perturbative contribution carries the factor `(-g)^n/n!`.
6. Because Altland writes the interaction as `g\phi^4` rather than `g\phi^4/4!`, the combinatorial multiplicities must be counted explicitly.
7. Vacuum bubbles from the numerator cancel against the denominator of the expectation value, so the Green function is built only from **connected diagrams**.

In momentum space the rules become even cleaner:

1. Each internal line contributes `G_0(p)=1/(p^2+r)`.
2. Each vertex conserves momentum: the sum of incoming momenta is zero.
3. One integrates over all unconstrained internal loop momenta.
4. The number of independent momentum integrals equals the number of loops.

This is why momentum space is usually the practical language for calculations.

## 6. What the diagrams are telling us physically

The diagrams are not just bookkeeping devices. They separate different physical processes:

- connected vs disconnected diagrams;
- one-particle reducible vs one-particle irreducible diagrams;
- different loop orders, which often signal different levels of fluctuation effects.

This classification becomes useful because the full Green function can be reorganized through the **self-energy** `\Sigma`:

```math
G = G_0 + G_0 \Sigma G,
\qquad
G^{-1}=G_0^{-1}-\Sigma.
```

My understanding is that this is the conceptual payoff of the chapter: instead of summing raw diagrams forever, we collect the one-particle-irreducible parts into `\Sigma`, and then recover the full propagator through Dyson's equation. In other words, interactions modify propagation by dressing the bare Green function.

## 7. Important warnings from the chapter

Altland emphasizes that perturbation theory is powerful but dangerous:

- UV divergences appear because expressions like `G_0(0)` probe arbitrarily short distances.
- IR divergences appear near criticality when `r \to 0` and the correlation length becomes very large.
- The series itself is asymptotic, so higher order does not always mean better.

So the right attitude is not "expand forever," but rather "identify the important structures and resum them intelligently."

## 8. My summary of the chapter

My main takeaway is that the Green function is the central carrier of physical information in perturbation theory. In the free theory it tells us how fluctuations propagate; in the interacting theory it gets corrected by all possible scattering processes generated by `\phi^4`. Wick's theorem produces these corrections as sums over pairings, and Feynman diagrams turn that combinatorial mess into a readable structure.

For this reason, `\phi^4` theory is a perfect training ground. It teaches three key lessons at once:

1. perturbation theory is asymptotic;
2. Green functions encode correlations and critical behavior;
3. diagrammatics is the practical language for organizing interaction corrections.

So, to me, the chapter is really about learning to see an interacting field theory through its propagator: start from `G_0`, add interactions through diagrams, isolate the self-energy, and then reconstruct the full Green function.
