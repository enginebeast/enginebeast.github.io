---
title: "Electric fields"
categories:
    - physics_note
use_math: true
---

## Definition

Electric fields is defined by the following equation.

$$\vec{E} = \frac{\vec{F}}{q_0}$$

Where, $$q_0$$ is test charge which become the standard of electric fields.
And its SI unit is a newton per coulomb(N/C).

By the [Coulomb's law](https://enginebeast.github.io/physics_note/charge/), we can get the following equation.

$$\vec{E} = k_e \frac{qq_0}{r^2}\hat{r}\frac{1}{q_0} = \frac{1}{4\pi\epsilon_0}\frac{q}{r^2}\hat{r}$$

## The electric field due to several point charges

We can find the net electric field as follows.

$$\vec{E} = \sum^n_{i=1}\vec{E_i}$$

## The electric field due to an electric dipole
    
An electric dipole is a system consisting of two equal and opposite charges, q and -q, separated by certain distance.
The equation for a magnitude of its electric field is as follows.

$$E = k_e \frac{2q\vec{d}}{z^3}$$

Where d is a distance between two charge, and z is a distance between center of two charge and a test charge.

We can express $$q\vec{d}$$ as follows.

$$\vec{p} = q\vec{d}$$

And, we call $$\vec{p}$$ the electric dipole moment. Please remember it, because it uses too when studying the torque on an electric dipole.

<!--## Find electric fields using integral-->

## Torque of electric dipole
In classical mechanics, torque, $$\tau$$ is defined by the following equation.

$$\vec{\tau} = \vec{r} \times \vec{F}$$

And we now know the relation between force and the electric field.

$$\vec{F} = q\vec{E}$$

And by combining the first and second equations, we can get the following equation.

$$
\begin{aligned}
\vec{\tau} & = \vec{r} \times q\vec{E}
\\& =q\vec{r} \times \vec{E}
\\& =\vec{p} \times \vec{E}
\end{aligned}
$$