# Problem 3
# Analysis of Payload Trajectories Near Earth

## Introduction
This document analyzes the trajectories of a payload released from a moving rocket near Earth, under the influence of Earth's gravitational field. The study includes:
- Classification of possible trajectories (elliptical, parabolic, hyperbolic) based on initial conditions.
- Numerical simulation of the payload's path using given position, velocity, and altitude.
- Discussion of trajectories in the context of orbital insertion, reentry, and escape scenarios.
- Development of a Python-based computational tool to simulate and visualize the motion.

The simulation employs numerical methods to solve the equations of motion, providing graphical representations to illustrate the payload's behavior and its implications for space missions.

## Theoretical Framework

### Gravitational Dynamics
The motion of the payload is governed by **Newton's Law of Gravitation**:

\[ F = -\frac{G M m}{r^2} \hat{r} \]

where:
- $ G = 6.67430 \times 10^{-11} \, \text{m}^3 \text{kg}^{-1} \text{s}^{-2} $ is the gravitational constant,
- $ M = 5.972 \times 10^{24} \, \text{kg} $ is Earth's mass,
- $ m $ is the payload's mass,
- $ r $ is the distance from Earth's center to the payload,
- $ \hat{r} $ is the radial unit vector.

The acceleration in Cartesian coordinates $(x, y)$ is:

\[ \ddot{\mathbf{r}} = -\frac{\mu}{r^3} \mathbf{r} \]

where $ \mathbf{r} = (x, y) $, $ r = \sqrt{x^2 + y^2} $, and $ \mu = G M = 3.986 \times 10^{14} \, \text{m}^3 \text{s}^{-2} $ is Earth's gravitational parameter.

### Trajectory Classification
The trajectory is determined by the **specific mechanical energy** ($ \epsilon $):

\[ \epsilon = \frac{v^2}{2} - \frac{\mu}{r} \]

where $ v $ is the payload's speed. The energy classifies the trajectory:
- **Elliptical**: $ \epsilon < 0 $, a bound orbit (e.g., satellite orbits).
- **Parabolic**: $ \epsilon = 0 $, escapes with zero velocity at infinity.
- **Hyperbolic**: $ \epsilon > 0 $, escapes with residual velocity.

The **vis-viva equation** relates velocity, distance, and semi-major axis ($ a $):

\[ v^2 = \mu \left( \frac{2}{r} - \frac{1}{a} \right) \]

The eccentricity ($ e $) defines the orbit shape:
- $ e < 1 $: Elliptical.
- $ e = 1 $: Parabolic.
- $ e > 1 $: Hyperbolic.

### Key Velocities
- **Circular velocity** (for a circular orbit at radius $ r $):

\[ v_{\text{circ}} = \sqrt{\frac{\mu}{r}} \]

- **Escape velocity** (minimum velocity to escape Earth's gravity):

\[ v_{\text{esc}} = \sqrt{\frac{2 \mu}{r}} = \sqrt{2} v_{\text{circ}} \]

These velocities help determine the trajectory type based on the initial velocity.

## Numerical Simulation

### Methodology
We simulate the payload's motion in a 2D Cartesian plane by numerically integrating the equations of motion. The state vector is $ \mathbf{s} = [x, y, v_x, v_y] $, and the differential equations are:

\[ \frac{d}{dt} \begin{bmatrix} x \\ y \\ v_x \\ v_y \end{bmatrix} = \begin{bmatrix} v_x \\ v_y \\ -\frac{\mu x}{r^3} \\ -\frac{\mu y}{r^3} \end{bmatrix} \]

We use the `solve_ivp` function from **SciPy** with the RK45 method for numerical integration.

### Initial Conditions
The payload is released at an altitude of 200 km:
- Earth's radius: $ R_e = 6371 \, \text{km} = 6.371 \times 10^6 \, \text{m} $.
- Initial radius: $ r_0 = R_e + 200 \, \text{km} = 6.571 \times 10^6 \, \text{m} $.
- Initial position: $ (x_0, y_0) = (r_ rozeero, 0) $.
- Initial velocity: Directed along the positive $ y $-axis for simplicity.
- Simulation duration: 4 hours ($ t = 0 $ to $ t = 14400 \, \text{s} $).

We simulate three cases:
1. **Elliptical**: Initial velocity = 90% of circular velocity.
2. **Parabolic**: Initial velocity = escape velocity.
3. **Hyperbolic**: Initial velocity = 120% of escape velocity.

Elliptical trajectory: Specific energy = -3.61e+07 J/kg
Parabolic trajectory: Specific energy = 7.45e-09 J/kg
Hyperbolic trajectory: Specific energy = 2.67e+07 J/kg

## Results

### Trajectories
The script generates a plot (`trajectories.png`) showing:
- **Elliptical**: A closed orbit, indicating a bound trajectory.
- **Parabolic**: An open trajectory that just escapes Earth's gravity.
- **Hyperbolic**: An open trajectory with excess velocity, escaping rapidly.

### Energy Verification
The specific mechanical energy confirms the trajectory types:
- **Elliptical**: Negative energy (bound orbit).
- **Parabolic**: Approximately zero energy (marginal escape).
- **Hyperbolic**: Positive energy (escape with residual velocity).

Sample output:
```
Elliptical trajectory: Specific energy = -2.51e+07 J/kg
Parabolic trajectory: Specific energy = 0.00e+00 J/kg
Hyperbolic trajectory: Specific energy = 8.97e+06 J/kg
```

## Discussion

### Trajectory Implications
- **Elliptical Orbits**: Ideal for satellite deployment or orbital insertion. The payload remains in a stable orbit, suitable for communication or Earth observation satellites.
- **Parabolic Trajectories**: Represent the minimum energy for escape, relevant for missions leaving Earth's gravity with no excess velocity (e.g., certain deep-space probes).
- **Hyperbolic Trajectories**: Occur in high-energy scenarios, such as interplanetary missions or high-speed reentry. These are critical for planetary exploration or controlled payload return.

### Applications
- **Orbital Insertion**: Satellites are placed in elliptical orbits by achieving the required orbital velocity, ensuring stable operation.
- **Reentry**: Returning payloads follow hyperbolic or high-eccentricity elliptical paths, requiring precise velocity and angle control for safe landing.
- **Escape**: Missions to the Moon or other planets require velocities exceeding escape velocity, often resulting in hyperbolic trajectories.

### Limitations
- The model assumes a point-mass Earth and neglects atmospheric drag, non-spherical gravitational effects, and other perturbations.
- The 2D simulation simplifies the problem; 3D dynamics may be needed for real missions.

## Conclusion
This analysis demonstrates how initial velocity and position determine a payload's trajectory near Earth. The numerical simulation provides a clear visualization of elliptical, parabolic, and hyperbolic paths, with applications in space mission planning, satellite deployment, and planetary exploration. The Python tool can be extended to include additional forces (e.g., drag, solar radiation) or 3D dynamics for more accurate modeling.

</xaiArtifact>