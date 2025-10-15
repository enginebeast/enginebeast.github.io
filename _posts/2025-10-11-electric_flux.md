---
title: "Electric flux and Gauss' law"
categories:
    - physics_note
use_math: true
---

<h2>Definition of electric flux</h2>

    We define electric flux by following equation.
    $$
    \begin{flalign*}
    \Phi = \oint\vec{E}\cdot d\vec{A} &&
    \end{flalign*}
    $$

    We can calculate differential normal area(\(d\vec{A}\)) using the following formula.<br>
    <br>
    For rectangular box,<br>
    <br>
    \(d\vec{A} = dxdy\hat{z}\)   or   \(d\vec{A} = dydz\hat{x}\)   or   \(d\vec{A} = dzdx\hat{y}\)<br>
    <br>
    <img width="1524" height="881" alt="Image" src="https://github.com/user-attachments/assets/3f25213b-88bf-41dc-b2f6-20ec0f8a47d7" />
    For top or bottom of cylinder,
    $$
    \begin{flalign*}
    d\vec{A} = rdrd\theta\hat{z} &&
    \end{flalign*}
    $$

    For side of cylindal,
    $$
    \begin{flalign*}
    d\vec{A} = rd\theta dz\hat{r} &&
    \end{flalign*}
    $$

    <img width="1524" height="881" alt="Image" src="https://github.com/user-attachments/assets/6ed16e85-c4de-4bed-a5f0-39c022d54ee3" />
    For surface of sphere,
    $$
    \begin{flalign*}
    d\vec{A} = r^2 \sin\phi d\theta d\phi \hat{r} &&
    \end{flalign*}
    $$
    
<h2>Gauss' law</h2>

    After trying to find electric flux, we would realize that it is not easy to calculate it using only its mathematical definition.
    For this reason, we can use Gauss' law which is a method to solve electric flux problems more easier.

    $$
    \begin{flalign*}
    \Phi = \frac{q_{enc}}{\epsilon_0} &&
    \end{flalign*}
    $$

    Where \(q_{enc}\) is net charge, and \(\epsilon_0\) is permittivity of free space.<br>
    <br>
    If \(q_{enc}\) is positive, a net flux heads to the outside. 
    And if \(q_{enc}\) is negative, a net flux heads to the inside.
