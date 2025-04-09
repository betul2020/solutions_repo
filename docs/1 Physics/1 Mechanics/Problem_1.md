# Investigating the Range as a Function of the Angle of Projection

## 1. Theoretical Foundation

Projectile motion is a classic problem in mechanics that describes the motion of an object under the influence of gravity alone, neglecting air resistance initially. Let’s derive the governing equations from Newton’s second law and establish the family of solutions based on initial conditions.

### Derivation of Equations of Motion

Consider a projectile launched from the origin $(x_0, y_0) = (0, 0)$ with an initial velocity $v_0$ at an angle $\theta$ to the horizontal. The only force acting is gravity, with acceleration $g$ downward. We break the motion into horizontal ($x$) and vertical ($y$) components.

- *Horizontal motion*: No acceleration, so:
  $$
  a_x = 0
  $$

  Initial velocity: $v_{0x} = v_0 \cos\theta$
  Position: 

  $$
  x(t) = v_0 \cos\theta \cdot t
  $$

- *Vertical motion*:

 Acceleration due to gravity, $a_y = -g$:

  Initial velocity: $v_{0y} = v_0 \sin\theta$
  Velocity: 

  $$
  v_y(t) = v_0 \sin\theta - g t
  $$

  Position: 

  $$
  y(t) = v_0 \sin\theta \cdot t - \frac{1}{2} g t^2
  $$

These are parametric equations describing a parabolic trajectory. The family of solutions depends on the free parameters: $v_0$ (initial speed), $\theta$ (angle of projection), and $g$ (gravitational acceleration). Varying these parameters generates different trajectories.

## 2. Analysis of the Range

The *range* $R$ is the horizontal distance traveled when the projectile returns to $y = 0$. Set $y(t) = 0$ and solve for time of flight $t_f$:

$$
0 = v_0 \sin\theta \cdot t - \frac{1}{2} g t^2
$$

Factorize:

$$
t \left( v_0 \sin\theta - \frac{1}{2} g t \right) = 0
$$

Solutions:

- $t = 0$ (launch)
- $t = \frac{2 v_0 \sin\theta}{g}$ (landing)

Substitute $t_f = \frac{2 v_0 \sin\theta}{g}$ into the horizontal equation:

$$
R = x(t_f) = v_0 \cos\theta \cdot \frac{2 v_0 \sin\theta}{g}
$$

Using the identity $2 \sin\theta \cos\theta = \sin 2\theta$:

$$
R = \frac{v_0^2 \sin 2\theta}{g}
$$

### Dependence on Angle $\theta$

- Range $R$ is maximized when $\sin 2\theta = 1$, i.e., $2\theta = 90^\circ$, so $\theta = 45^\circ$.
- $R = 0$ when $\theta = 0^\circ$ or $\theta = 90^\circ$ (no horizontal motion).
- The relationship is symmetric: $\theta$ and $(90^\circ - \theta)$ yield the same range.

### Influence of Other Parameters

- *Initial velocity $v_0$*: $R \propto v_0^2$, a quadratic increase.
- *Gravitational acceleration $g$*: $R \propto \frac{1}{g}$, inversely proportional.

## 3. Practical Applications

This idealized model applies to:

- *Sports*: Trajectories of balls in soccer, basketball, or golf.
- *Engineering*: Artillery or rocket launches.
- *Astrophysics*: Simplified planetary motion (with adjusted $g$).

For real-world scenarios:

- *Uneven terrain*: Adjust $y_0$ or solve for $y(x)$ intersecting a surface.
- *Air resistance*: Introduce a drag term, e.g., $-k v$, requiring numerical solutions.

## 4. Implementation

Below is a Python script using NumPy and Matplotlib to simulate and visualize the range as a function of $\theta$ for different $v_0$ and $g$.

![alt text](<WhatsApp Image 2025-04-09 at 16.29.29_a4b35d6c-1.jpg>)
## Discussion on Model Constrains

The basic model assumes:

- Absence of air friction: In reality, projectiles lose speed, which decreases their travel distance.
- Flat landscape: Uneven ground affects the landing position.
- Steady $g$: Gravitational pull varies slightly depending on altitude or celestial body.

### Possible Improvements

- *Drag Force*: Include a term such as $-k v$ in the motion equations and solve them numerically (e.g., with scipy.integrate.odeint).
- *Wind Influence*: Add a horizontal wind speed component to the calculations.
- *Initial Height*: Use a non-zero $y_0$ and determine $t_f$ by solving the resulting quadratic equation.

## Final Thoughts

Though projectile motion appears straightforward, it holds significant depth. The range’s variation with $\theta$, peaking at $45^\circ$, and its dependence on $v_0$ and $g$ showcase a adaptable framework relevant to numerous disciplines. Simulations provide visual insight into these patterns, while enhancements like drag or terrain adjustments align the model more closely with practical scenarios.
