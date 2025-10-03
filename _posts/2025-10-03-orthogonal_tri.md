---
title: "Fourier series"
categories:
    - math_note
use_math: true
comments: true
---

### Formulas
$$
\begin{flalign*}
&\int_{-\pi}^\pi \cos nx \cos mx = 
\begin{cases} 
0 & (n \neq m)
\\ \pi & (n = m \neq 0)
\\ 2\pi & (n = m = 0)
\end{cases}\\
\\ 
&\int_{-\pi}^\pi \sin nx \sin mx = 
\begin{cases} 
0 & (n \neq m)
\\ \pi & (n = m \neq 0)
\\ 0 & (n = m = 0)
\end{cases}\\
\\ 
&\int_{-\pi}^\pi \sin nx \cos mx = 0 
\end{flalign*}
$$

### Derivation
(i)  
First, we can apply [trigonometric addition formulas](https://enginebeast.github.io/math1/).

$$
\begin{flalign*}
& \cos nx \cos mx = \frac{1}{2}\cos(n-m)x + \frac{1}{2}\cos(n+m)x\\
\\
& \Rightarrow \int_{-\pi}^\pi \cos nx \cos mx =\frac{1}{2}\int_{-\pi}^\pi\cos(n-m)x + \frac{1}{2}\int_{-\pi}^\pi\cos(n+m)x
\end{flalign*}
$$

By the symmetry of the cosine function about the x-axis, we can derive the result as follows.

$$
\begin{flalign*}
\int_{-\pi}^\pi \cos nx \cos mx = 
\begin{cases} 
0 & (n \neq m)
\\ \pi & (n = m \neq 0)
\\ 2\pi & (n = m = 0)
\end{cases} &&
\end{flalign*}
$$

(ii)  
Derivation of (ii) is similar to the one in (i).

$$
\begin{flalign*}
& \sin nx \sin mx = \frac{1}{2}\cos(n-m)x - \frac{1}{2}\cos(n+m)x\\
\\
& \Rightarrow \int_{-\pi}^\pi \sin nx \sin mx =\frac{1}{2}\int_{-\pi}^\pi\cos(n-m)x - \frac{1}{2}\int_{-\pi}^\pi\cos(n+m)x\\
\\
& \Rightarrow \int_{-\pi}^\pi \sin nx \sin mx = 
\begin{cases} 
0 & (n \neq m)
\\ \pi & (n = m \neq 0)
\\ 0 & (n = m = 0)
\end{cases}
\end{flalign*}
$$


(iii)  
Applying trignometric addtion formulas is same.

$$
\begin{flalign*}
&\sin nx \cos mx = \frac{1}{2}\sin(n+m)x + \frac{1}{2}\sin(n-m)x \\
\\
&\Rightarrow \int_{-\pi}^\pi \sin nx \cos mx = \frac{1}{2}\int_{-\pi}^\pi\sin(n+m)x + \frac{1}{2}\int_{-\pi}^\pi\sin(n-m)x\\
\end{flalign*}
$$

However, by the symmetry of the sine function about the origin, the result of the formula is always 0.

$$ 
\begin{flalign*}
\int_{-\pi}^\pi \sin nx \cos mx = 0 &&
\end{flalign*}
$$
