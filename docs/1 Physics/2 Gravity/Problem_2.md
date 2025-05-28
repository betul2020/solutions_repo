Escape Velocities and Cosmic Velocities

Motivation

The concept of escape velocity is crucial for understanding the conditions required to leave a celestial body's gravitational influence. Extending this concept, the first, second, and third cosmic velocities define the thresholds for orbiting, escaping, and leaving a star system. These principles underpin modern space exploration, from launching satellites to interplanetary missions.

Task

1. Definitions and Physical Meaning

First Cosmic Velocity (Orbital Velocity): The minimum speed required for an object to maintain a stable orbit around a celestial body without falling back or drifting away. For a circular orbit, it depends on the body's mass and the orbital radius. Physically, it balances gravitational pull with centrifugal force.

Second Cosmic Velocity (Escape Velocity): The speed needed for an object to escape the gravitational influence of a celestial body entirely, reaching infinity with zero kinetic energy. It is the threshold to break free from the body's gravity.

Third Cosmic Velocity (Escape from Star System): The speed required to escape the gravitational pull of a star system (e.g., the Solar System), considering the mass of the star and the distance from it. This applies to interstellar travel.

![alt text](image-4.png)
2. Mathematical Derivations and Parameters

The velocities can be derived using gravitational principles. Let’s denote:


$G$ = Gravitational constant ($6.674 \times 10^{-11} , \text{m}^3 \text{kg}^{-1} \text{s}^{-2}$)

$M$ = Mass of the celestial body (kg)


$R$ = Radius of the orbit or body (m)


$m$ = Mass of the object (kg, often cancels out)

First Cosmic Velocity

For a circular orbit: $ v_1 = \sqrt{\frac{GM}{R}} $

This arises from equating gravitational force to centripetal force: $ \frac{GMm}{R^2} = \frac{mv_1^2}{R} $.

Second Cosmic Velocity


![alt text](<Screenshot 2025-05-28 161637.png>)

3. Calculations and Visualizations

Below is a Python script to calculate and visualize the velocities for Earth, Mars, and Jupiter. The script uses matplotlib for graphical representations.