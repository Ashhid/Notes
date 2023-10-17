1. Parallel axis theorem
	Let's consider This diagram
![[../Imgs/idk.jpg|200]]
- Let's consider this small part with the mass of $m_i$.
- And a axis which passes through the center of the mass with the name of $XX\prime$.
- And a axis which is parallel to the $XX\prime$ let's name it $AA\prime$.
- And the distance between them let's name it $x$

Moment of inertia wrt, x axis.
$$
	dI = m_i r_i^2 
$$
Moment of inertia wrt to the entire body.
$$
I_{XX\prime} =  \sum dI_{XX\prime} = \sum m_i r_i^2
$$
Now, for the $AA\prime$ Axis.
$$
dI_{AA\prime} = m_i(r_i + x)^2
$$
Now, for the moment of inertia wrt, to the entire body.
$$
dI_{AA\prime} = \sum m_i(r_i + x)^2
$$
$$
dI_{AA\prime} = \sum m_i(r_i^2 + 2r_ix + x^2)
$$
$$
dI_{AA\prime} = \sum m_ir_i^2 + \sum m_i2r_ix + \sum m_ix^2
$$
Substituting $\sum m_ir_i^2$ As $I_{XX\prime}$, and $\sum 2m_ix$ as 0 cause the total momentum is equal 0. and $\sum m_i x^2$ as $M$ cause it's the total mass of the body.
$$
dI_{AA\prime} = I_{XX\prime} + 0 + Mx^2
$$
---
2. Perpendicular Axis Theorem
![[WhatsApp Image 2023-10-16 at 23.14.07_dac79963.jpg|200]]
- Let's assume a 3 axis since it's a 3d body. $XX\prime$, $YY\prime$ And $ZZ\prime$.
- And as we know there 3 are perpendicular to each other since they are a coordinate system.

The Moment of inertia of the thin plane wrt, $XX\prime$ is
$$
dI_{XX\prime} = m_ir_i^2
$$
The Moment of inertia of the thin plane wrt to the whole body is
$$
I_{XX\prime} = \sum m_ir_i^2
$$
As we can see by applying vector addition to the diagram we can get
$$
r_i^2 = y_i^2 + x_i^2
$$
Now, we can substitute the above equation with the top equation and we get.
$$
I_{XX\prime} = \sum m_i(y_i^2 + z_i^2)
$$
$$
I_{XX\prime} = \sum m_iy_i^2 + \sum m_iz_i^2
$$
we know that, the sum of $m_iy_i^2$ and $m_iz_i^2$ is $I_{YY\prime}$ and $I_{ZZ\prime}$
$$
I_{XX\prime} = I_{YY\prime} + I_{ZZ\prime} 
$$
---
3. Torsional Pendulum
Let's consider this Diagram
![[WhatsApp Image 2023-10-16 at 23.52.24_6d79ec3b.jpg|200]]
Restoring couple through an angle $\theta$. is:
$$
\theta = \int_{0}^{\theta} Moment\;of\;couple \times d\theta
$$

$$
P.E = \int_{0}^{\theta} C \theta. d\theta
$$
$$
P.E. = \frac{C\theta^2}{2}
$$
And we know,
$$
K.E. = \frac{1}{2}I \omega^2
$$
And when we sum these both energies we get the total energy which is a constand.
$$
Total \; Energy = \frac{C\theta^2}{2} + \frac{I \omega^2}{2} = constant
$$
Diff wrt, t.
$$
T = \frac{1}{2}\{ \frac{d(C\theta^2)}{dt}+\frac{d(I\omega^2)}{dt}\} = 0
$$
$$
T = C\theta \frac{d\theta}{dt} + I\omega \frac{d\omega}{dt} = 0
$$
Now, $\omega = \frac{d\theta}{dt}$,
$$
T = C\theta\frac{d\theta}{dt} + I\frac{d\theta}{dt}\frac{d^2\theta}{dt^2} = 0
$$
Taking $\frac{d\omega}{dt}$ as common,
$$ 
\frac{d\theta}{dt}\biggl(C\theta + I\frac{d^2\theta}{dt^2} \biggl) = 0
$$
Here, only the 2nd term that is $C\theta + I\frac{d\theta}{dt}$ can be 0 since $\frac{d\theta}{dt}$ is non 0 term.
So, We can say

$$
C\theta + I\frac{d^2\theta}{dt^2} = 0
$$
$$
I\frac{d^2\theta}{dt^2} = -C\theta
$$
$$
\frac{d^2\theta}{dt^2} = \frac{-C\theta}{I}
$$
This the term $\frac{d^2\theta}{dt^2}$ is called angular acceleration.

Period Of Occillation.
