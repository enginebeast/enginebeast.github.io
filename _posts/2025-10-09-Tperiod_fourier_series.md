---
title: "Arbitrary T period Fourier series"
categories:
    - math_note
use_math: true
comments: true
---

## Definition of Fourier series

$$
f(t) = a_0 
+ \sum^\infty_{n=1} a_n \cos(n\omega_0 t)
+ \sum^\infty_{n=1} b_n \sin(n\omega_0 t)
$$

Formula of Fourier coefficients
  
$$
\begin{aligned}
& a_0 = \frac{1}{T}\int_0^T f(t)\,dt \\
\\
& a_n = \frac{2}{T}\int_0^T f(t)\cos(n\omega_0 t)\,dt \\
\\
& b_n = \frac{2}{T}\int_0^T f(t)\sin(n\omega_0 t)\,dt
\end{aligned}
$$

## Fourier coefficients for even function

$$
\begin{aligned}
& a_0 = \frac{2}{T}\int^{T/2}_0 f(t)\,dt \\
\\
& a_n = \frac{4}{T}\int^{T/2}_0 f(t)\cos(n\omega_0 t)\,dt \\
\\
& b_n = 0
\end{aligned}
$$

## Fourier coefficients for odd function

$$
\begin{aligned}
& a_0 = 0
\\
& a_n = 0
\\
& b_n = \frac{4}{T}\int^{T/2}_0 f(t)\sin(n\omega_0 t)\,dt
\end{aligned}
$$
