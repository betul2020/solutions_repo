# Problem 2
Escape Velocities and Cosmic Velocities
Motivation
The concept of escape velocity is fundamental to understanding how objects can overcome a celestial body’s gravitational pull. The first, second, and third cosmic velocities extend this idea, defining thresholds for achieving orbit, escaping a planet, or leaving a star system. These principles are critical for space exploration, guiding the design of satellite launches, interplanetary missions, and potential interstellar travel.

Task Breakdown
Define the first, second, and third cosmic velocities, explaining their physical meaning.
Analyze the mathematical derivations and parameters affecting these velocities.
Calculate and visualize these velocities for Earth, Mars, and Jupiter.
Discuss their importance in space exploration, including applications in satellite launches, planetary missions, and interstellar travel.
Deliverables
A Markdown document with a Python script implementing calculations and visualizations.
Detailed explanations of the concepts.
Graphical representations of cosmic velocities for Earth, Mars, and Jupiter.
1. Definitions and Physical Meaning
First Cosmic Velocity ($v_1$)
The first cosmic velocity is the minimum speed required for an object to maintain a circular orbit around a celestial body at a given radius (typically near the surface). It represents the balance between gravitational attraction and centripetal force needed for orbital motion.

Physical Meaning: Achieving $v_1$ allows satellites to orbit without falling back to the surface or escaping into space.

Second Cosmic Velocity ($v_2$)
The second cosmic velocity, or escape velocity, is the speed required for an object to escape a celestial body’s gravitational field entirely, reaching infinity with zero residual velocity.

Physical Meaning: $v_2$ enables spacecraft to leave a planet’s influence, critical for interplanetary missions.

Third Cosmic Velocity ($v_3$)
The third cosmic velocity is the speed required for an object to escape the gravitational influence of a star system (e.g., the Sun) from the orbit of a planet (e.g., Earth). It accounts for the planet’s orbital velocity around the star.

Physical Meaning: $v_3$ is relevant for interstellar missions, such as sending probes beyond the solar system.

2. Mathematical Derivations and Parameters
First Cosmic Velocity ($v_1$)
For a circular orbit, the gravitational force equals the centripetal force:

$\frac{G M m}{r^2} = \frac{m v_1^2}{r}$

Where:

$G$: Gravitational constant ($6.67430 \times 10^{-11}$ m³ kg⁻¹ s⁻²)
$M$: Mass of the celestial body (kg)
$m$: Mass of the orbiting object (kg)
$r$: Orbital radius (m, typically the body’s radius for surface orbits)
$v_1$: Orbital velocity (m/s)
Cancel $m$ and multiply by $r$:

$\frac{G M}{r} = v_1^2$

Thus:

$v_1 = \sqrt{\frac{G M}{r}}$

Second Cosmic Velocity ($v_2$)
Escape velocity is derived from energy conservation. The total mechanical energy at the surface (kinetic + potential) equals zero at infinity (where potential energy is zero, and velocity is zero):

$\frac{1}{2} m v_2^2 - \frac{G M m}{r} = 0$

Simplify:

$\frac{1}{2} v_2^2 = \frac{G M}{r}$

$v_2^2 = \frac{2 G M}{r}$

Thus:

$v_2 = \sqrt{\frac{2 G M}{r}} = \sqrt{2} v_1$

Third Cosmic Velocity ($v_3$)
The third cosmic velocity is the speed needed to escape the Sun’s gravitational field from Earth’s orbit. Total energy to reach infinity from the Sun’s field at distance $r_{\text{AU}}$ (Earth’s orbital radius, 1 AU):

$\frac{1}{2} m v_{\text{total}}^2 - \frac{G M_{\text{Sun}} m}{r_{\text{AU}}} = 0$

$v_{\text{total}} = \sqrt{\frac{2 G M_{\text{Sun}}}{r_{\text{AU}}}}$

Earth orbits the Sun at $v_{\text{orbit}} \approx \sqrt{\frac{G M_{\text{Sun}}}{r_{\text{AU}}}}$, so the additional velocity from Earth’s surface (relative to Earth’s orbital velocity) is:

$v_3 = \sqrt{\frac{2 G M_{\text{Sun}}}{r_{\text{AU}}}} - \sqrt{\frac{G M_{\text{Sun}}}{r_{\text{AU}}}}

$v_3 \approx \sqrt{\frac{G M_{\text{Sun}}}{r_{\text{AU}}}} (\sqrt{2} - 1)$

Parameters Affecting Velocities
Mass ($M$): Higher mass increases $v_1$, $v_2$, and $v_3$.
Radius ($r$): Larger radius decreases velocities.
Star Mass ($M_{\text{Sun}}$): Affects $v_3$ for solar system escape.
3. Calculations for Earth, Mars, and Jupiter
Constants
$G = 6.67430 \times 10^{-11}$ m³ kg⁻¹ s⁻²
$M_{\text{Sun}} = 1.989 \times 10^{30}$ kg
$r_{\text{AU}} = 1.496 \times 10^{11}$ m (1 AU)
Celestial Bodies
Earth: $M = 5.972 \times 10^{24}$ kg, $r = 6,371 \times 10^3$ m
Mars: $M = 6.417 \times 10^{23}$ kg, $r = 3,390 \times 10^3$ m
Jupiter: $M = 1.898 \times 10^{27}$ kg, $r = 69,911 \times 10^3$ m
Calculations
Earth:
$v_1 = \sqrt{\frac{G \cdot 5.972 \times 10^{24}}{6.371 \times 10^6}}} \approx 7.91$ km/s
$v_2 = \sqrt{\frac{2 G \cdot 5.972 \times 10^{24}}{6.371 \times 10^6}}} \approx 11.19$ km/s
Mars:
$v_1 = \sqrt{\frac{G \cdot 6.417 \times 10^{23}}{3.390 \times 10^6}}} \approx 3.55$ km/s
$v_2 = \sqrt{\frac{2 G \cdot 6.417 \times 10^{23}}{3.390 \times 10^6}}} \approx 5.03$ km/s
Jupiter:
$v_1 = \sqrt{\frac{G \cdot 1.898 \times 10^{27}}{69,911 \times 10^6}}} \approx 42.14$ km/s
$v_2 = \sqrt{\frac{2 G \cdot 1.898 \times 10^{27}}{69,911 \times 10^6}}} \approx 59.54$ km/s
Third Cosmic Velocity (from Earth’s orbit):
$v_{\text{total}} = \sqrt{\frac{2 G \cdot 1.989 \times 10^{30}}{1.496 \times 10^{11}}}} \approx 42.13$ km/s
$v_{\text{orbit}} = \sqrt{\frac{G \cdot 1.989 \times 10^{30}}{1.496 \times 10^{11}}}} \approx 29.78$ km/s
$v_3 \approx 42.13 - 29.78 \approx 12.35$ km/s (from Earth’s surface, simplified).
Note: $v_3$ is approximate, as it depends on Earth’s velocity and launch direction.

4. Importance in Space Exploration
Satellite Launches: Achieving $v_1$ (e.g., 7.91 km/s for Earth) places satellites in low Earth orbit (LEO), critical for communication and Earth observation.
Interplanetary Missions: $v_2$ (e.g., 11.19 km/s for Earth) allows spacecraft to escape Earth for missions to Mars or Jupiter.
Interstellar Travel: $v_3$ (e.g., ~12.35 km/s from Earth) is necessary for probes like Voyager to leave the solar system, though gravitational assists often reduce this requirement.



Output Explanation
Bar Chart: Displays $v_1$ and $v_2$ for Earth, Mars, and Jupiter, and $v_3$ for Earth.
Console Output: Lists calculated velocities for clarity.
Earth: v1 = 7.91 km/s, v2 = 11.19 km/s
Mars: v1 = 3.55 km/s, v2 = 5.03 km/s
Jupiter: v1 = 42.14 km/s, v2 = 59.54 km/s
Earth: v3 = 12.35 km/s

Graphical Representations
The bar chart visualizes the significant differences in velocities due to varying masses and radii. Jupiter’s high velocities reflect its massive size, while Mars requires less energy to orbit or escape due to its smaller mass and radius. The third cosmic velocity for Earth highlights the challenge of interstellar missions.