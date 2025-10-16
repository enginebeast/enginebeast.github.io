---
title: "Electric flux and Gauss' law"
categories:
    - physics_note
use_math: true
---

<h2>Definition of electric flux</h2>

We define electric flux by following equation.  

 $$\Phi = \oint\vec{E}\cdot d\vec{A}$$

We can calculate $$d\vec{A}$$ using the following formula.  
  
For rectangular box,  

$$d\vec{A} = dxdy\hat{z}$$ 

or 

$$d\vec{A} = dydz\hat{x}$$

or

$$d\vec{A} = dzdx\hat{y}$$
  
<img width="1524" height="881" alt="Image" src="https://github.com/user-attachments/assets/a6d440aa-917a-473a-9530-e6304b8fbbf3" />

For top or bottom of cylinder,
  
$$d\vec{A} = rdrd\theta\hat{z}$$

For side of cylindal,
  
$$d\vec{A} = rd\theta dz\hat{r}$$

<img width="1524" height="881" alt="Image" src="https://github.com/user-attachments/assets/0def6749-de92-47d5-926d-393c4a84be6e" />

For surface of sphere,  

$$d\vec{A} = r^2 \sin\phi d\theta d\phi \hat{r}$$
    
<h2>Gauss' law</h2>

After trying to find electric flux, we would realize that it is not easy to calculate it using only its mathematical definition.
For this reason, we can use Gauss' law which is a method to solve electric flux problems more easier.

$$\Phi = \frac{q_{enc}}{\epsilon_0}$$

Where $$q_{enc}$$ is net charge, and $$\epsilon_0$$ is permittivity of free space.  
  
If $$q_{enc}$$ is positive, a net flux heads to the outside. 
And if $$q_{enc}$$ is negative, a net flux heads to the inside.
