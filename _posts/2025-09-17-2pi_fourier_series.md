---
title: "2 Pi period Fourier series"
categories:
    - math_note
use_math: true
comments: true
---

### Definition of Fourier series
$$f(x) = a_0 + \sum^\infty_{n=1} a_n \cos nx + \sum^\infty_{n=1} b_n \sin nx$$
  

### Formula of Fourier coefficients

$$
\begin{aligned}
& a_0 = \frac{1}{2\pi}\int^\pi_{-\pi}f(x)dx
\\
\\ & a_n = \frac{1}{\pi}\int^\pi_{-\pi}f(x)\cos nxdx
\\
\\ & b_n = \frac{1}{\pi}\int^\pi_{-\pi}f(x)\sin nxdx
\end{aligned}
$$  
  

### Derivation of $$a_0$$
$$
\begin{aligned}
\int^\pi_{-\pi}f(x)dx &= \int^\pi_{-\pi} \Bigg[ a_0 + \sum^\infty_{n=1} a_n \cos nx + \sum^\infty_{n=1} b_n \sin nx \Bigg]dx
\\
\\ &=\int^\pi_{-\pi} a_0 + \sum^\infty_{n=1}\int^\pi_{-\pi}a_n\cos nxdx + \sum^\infty_{n=1}\int^\pi_{-\pi}b_n\sin nxdx
\\
\\ &=2\pi a_0 + 0 + 0
\\
\\ &=2\pi a_0
\\
\end{aligned}
$$

$$
\begin{aligned}
\Rightarrow a_0 = \frac{1}{2\pi}\int^\pi_{-\pi}f(x)dx
\end{aligned}
$$  


### Derivation of $$a_n$$
$$
\begin{align}
\int^\pi_{-\pi}f(x)\cos ndx &= \int^\pi_{-\pi} \Bigg[ a_0 + \sum^\infty_{m=1} a_m \cos mx + \sum^\infty_{m=1} b_m \sin mx \Bigg]\cos nxdx
\\
\\ & = \int^\pi_{-\pi}a_0\cos nxdx + \sum^\infty_{m=1}\int^\pi_{-\pi}a_m \cos mx\cos nxdx + \sum^\infty_{m=1}\int^\pi_{-\pi}b_m \sin mx\cos nxdx
\\
\\ & =0 + \pi a_n + 0
\\
\\ & = \pi a_n 
\\
\end{align}
$$
$$
\begin{align}
\\
\\
\Rightarrow a_n = \frac{1}{\pi}\int^\pi_{-\pi}f(x)\cos nxdx
\end{align}
$$  


### Derivation of $$b_n$$
$$
\begin{align}
\int^\pi_{-\pi}f(x)\sin ndx &= \int^\pi_{-\pi} \Bigg[ a_0 + \sum^\infty_{m=1} a_m \cos mx + \sum^\infty_{m=1} b_m \sin mx \Bigg]\sin nxdx
\\
\\ & = \int^\pi_{-\pi}a_0\sin nxdx + \sum^\infty_{m=1}\int^\pi_{-\pi}a_m \cos mx\sin nxdx + \sum^\infty_{m=1}\int^\pi_{-\pi}b_m \sin mx\sin nxdx
\\
\\ & =0 + 0 + \pi b_n
\\
\\ & = \pi b_n 
\\
\end{align}
$$
$$
\begin{align}
\\
\\
\Rightarrow b_n = \frac{1}{\pi}\int^\pi_{-\pi}f(x)\sin nxdx
\end{align}
$$
