As parts of my semester project in the theory group at EPFL, I studied
how well we can round fractional values within matroid polytopes in an
online fashion. There is a lack of understanding on the online version
of this problem, although many researchs on offline rounding are in the
literature.

In this blog I will go through (on a high level) how I approached the
problem, under graphic matroid conditions.

\### TL;DR:

\*\*Theorem\*\*: There exist graphic matroid ODRSes with rounding ratio
$\frac{2}{\sqrt{27}} \cdot \frac{1}{\sqrt{n}}$, where $n$ is the number
of vertices in the graph.

This result is not tight and I believe that there would exist an
algorithm with $O(\frac{1}{\log n})$ rounding ratio.

\### Problem definition

Formally, we are given a matroid $\mathcal{M} = (E, \mathcal{I})$, and a
polytope relaxation $P_\mathcal{\mathcal{M}}$, which is usually
$\textnormal{conv}(\left\{\mathds{1}_{\left[I\right]} | I \in \mathcal{I{}}\right\})$.
The elements of $E$ arrive one by one, and when an element $e$ arrives
with its associated fractional value $x_e$, the algorithm must decide
irrevocably whether to choose it or not. At all times, the set of
currently selected elements $I$ must satisfy $I \in \mathcal{I}$. The
objective of ODRSes is to pick each element $e$ with probability at
least $\alpha \cdot x_e$ for $\alpha \in [0, 1]$ as large as possible.

\### Warm-ups

\### Main idea: contraction
