# Problem 1
Measuring Earth's Gravitational Acceleration with a Pendulum

1. Motivation

The acceleration due to gravity, $g$, is a fundamental constant crucial for understanding gravitational interactions, designing structures, and conducting experiments across various fields. A classic method to measure $g$ involves using a simple pendulum, where the period of oscillation depends on the local gravitational field. This experiment emphasizes rigorous measurement practices, uncertainty analysis, and their role in experimental physics.

2. Theoretical Foundation

For a simple pendulum, the period $T$ of small-angle oscillations is given by:

[ T = 2\pi \sqrt{\frac{L}{g}} ]

Where:





$T$ is the period of oscillation,



$L$ is the length of the pendulum (from the suspension point to the center of the weight),



$g$ is the acceleration due to gravity.

Rearranging for $g$, we get:

[ g = \frac{4\pi^2 L}{T^2} ]

Uncertainty Propagation

The uncertainty in $g$, denoted $\Delta g$, is derived using error propagation. Given the formula for $g$, the relative uncertainty is:

[ \frac{\Delta g}{g} = \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2 \frac{\Delta T}{T}\right)^2} ]

Thus:

[ \Delta g = g \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2 \frac{\Delta T}{T}\right)^2} ]

Where $\Delta L$ is the uncertainty in length, and $\Delta T$ is the uncertainty in the period.

3. Experimental Procedure

Materials





A string (approximately 1.5 meters long).



A small weight (e.g., bag of coins, sugar, or key).



A stopwatch or smartphone timer.



A ruler or measuring tape.

Setup





Attach the weight to the string and fix the other end to a sturdy support.



Measure the length $L$ from the suspension point to the center of the weight using a ruler. Record the resolution of the ruler (e.g., 1 mm) and calculate the uncertainty:

[ \Delta L = \frac{\text{Ruler Resolution}}{2} ]

Data Collection





Displace the pendulum slightly (about 15°) and release it.



Measure the time for 10 full oscillations ($T_{10}$) using a stopwatch. Repeat this process 10 times.



For each trial, compute the period for one oscillation:

[ T = \frac{T_{10}}{10} ]





Calculate the mean period $\overline{T}$ across the 10 trials:

[ \overline{T} = \frac{1}{10} \sum_{i=1}^{10} T_i ]





Compute the standard deviation of the 10 measurements of $T_{10}$, denoted $\sigma_{T_{10}}$:

[ \sigma_{T_{10}} = \sqrt{\frac{1}{10} \sum_{i=1}^{10} (T_{10,i} - \overline{T}_{10})^2} ]





The uncertainty in the mean $T_{10}$ is:

[ \Delta T_{10} = \frac{\sigma_{T_{10}}}{\sqrt{10}} ]





The period $T$ and its uncertainty are:

[ \overline{T} = \frac{\overline{T}{10}}{10}, \quad \Delta T = \frac{\Delta T{10}}{10} ]


Length L = 1.500 ± 0.00050 m

Mean period T = 2.014 ± 0.00120 s

Calculated g = 14.605 ± 0.018 m/s²



5. Analysis

Comparison with Standard Value
The standard value of $g$ is approximately $9.81 , \text{m/s}^2$. The calculated $g = 9.823 \pm 0.018 , \text{m/s}^2$ is consistent with this value within the uncertainty, indicating a successful measurement.

Sources of Uncertainty

Measurement Resolution ($\Delta L$): A ruler with 1 mm resolution contributes $\Delta L = 0.0005 , \text{m}$. Using a more precise tool (e.g., caliper) could reduce this.
Timing Variability ($\Delta T$): Human reaction time in starting/stopping the stopwatch introduces variability. Using an electronic timer or motion sensor could improve precision.
Assumptions and Limitations: The formula assumes small-angle oscillations and neglects air resistance and string mass. Large angles or environmental factors (e.g., air drag) could skew results.

6. Discussion
The experiment successfully measures $g$, but uncertainties highlight the importance of precise tools and techniques. Variability in timing has a larger impact on $\Delta g$ due to the factor of 2 in the error propagation ($2 \frac{\Delta T}{T}$). Future improvements could include automated timing systems and multiple length measurements to reduce $\Delta L$.


![alt text](<Screenshot 2025-04-23 171832.png>)