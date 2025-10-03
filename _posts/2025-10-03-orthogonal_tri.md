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

<img width="468" height="197" alt="image" src="https://github.com/user-attachments/assets/ecee5123-27cf-47ae-bea6-1d355866c4c9" />


(iii)  
Applying trignometric addtion formulas is same.

<img width="356" height="58" alt="image" src="https://github.com/user-attachments/assets/876b8c9b-6e06-4be8-aa27-2d7e318e7c4b" />

However, by the symmetry of the sine function about the origin, the result of the formula is always 0.

<img width="435" height="98" alt="image" src="https://github.com/user-attachments/assets/5f2f55ed-b26e-4c28-aa48-7505e2123027" />
