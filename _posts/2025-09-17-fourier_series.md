---
title: "Engine Beast : Alpha"
description: "Fourier series"
use_math: true
---

### Definition of Fourier series
$$
\begin{align}
f(x) = a_0 + \sum^\infty_{n=1} a_n \cos nx + \sum^\infty_{n=1} b_n \sin nx
\end{align}
$$

### Formula of Fourier coefficients
$$
\begin{align}
& a_0 = \frac{1}{2\pi}\int^\pi_{-\pi}f(x)dx
\\
\\ & a_n = \frac{1}{\pi}\int^\pi_{-\pi}f(x)\cos nxdx
\\
\\ & b_n = \frac{1}{\pi}\int^\pi_{-\pi}f(x)\sin nxdx
\end{align}
$$

### Derivation of $$a_0$$
$$
\begin{align}
\int^\pi_{-\pi}f(x)dx &= \int^\pi_{-\pi} \Bigg[ a_0 + \sum^\infty_{n=1} a_n \cos nx + \sum^\infty_{n=1} b_n \sin nx \Bigg]dx
\\
\\ &=\int^\pi_{-\pi} a_0 + \sum^\infty_{n=1}\int^\pi_{-\pi}a_n\cos nxdx + \sum^\infty_{n=1}\int^\pi_{-\pi}b_n\sin nxdx
\\
\\ &=2\pi a_0 + 0 + 0
\\
\\ &=2\pi a_0
\\
\end{align}
$$
$$
\\
\Rightarrow a_n = \frac{1}{\pi}\int^\pi_{-\pi}f(x)\cos nxdx
$$
