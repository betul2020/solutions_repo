# Problem 1
# Measuring Earth's Gravitational Acceleration with a Pendulum

## Motivation
The acceleration due to gravity g is a fundamental constant that influences a wide range of physical phenomena. Measuring g accurately is crucial for understanding gravitational interactions, designing structures, and conducting experiments in various fields. One classic method for determining g is through the oscillations of a simple pendulum, where the period of oscillation depends on the local gravitational field.

## Task
Measure the acceleration due to gravity g using a pendulum and detail the uncertainties in the measurements. This exercise emphasizes rigorous measurement practices, uncertainty analysis, and their role in experimental physics.

## Procedure

### 1. Materials
- A string (1.5 meters long).
- A small weight (e.g., bag of coins, bag of sugar, key chain) mounted on the string.
- A stopwatch or smartphone timer.

### 2. Setup
- Attach the weight to the string and fix the other end to a sturdy support.
- Measure the length of the pendulum L from the suspension point to the center of the weight using a ruler or measuring tape. Record the resolution of the measuring tool and calculate the uncertainty as half the resolution, Delta L = Ruler Resolution/2.

### 3. Data Collection
- Displace the pendulum slightly (5°–15°) and release it.
- Measure the time for 10 full oscillations (T10) and repeat this process 10 times. Record all measurements.
- Calculate the mean time for 10 oscillations (T10 bar) and the standard deviation (sigma T).
- Determine the uncertainty in the mean time as: Delta T = sigma T / square root of n, where n = 10.

## Calculations
1. Calculate the period: T = T10 / 10 and Delta T = Delta T10 / 10
2. Determine g: g = 4 pi squared L / T squared
3. Propagate uncertainties: Delta g = g [ (Delta L / L) squared + (2 Delta T / T) squared ] to the power of 1/2

## Analysis
1. Compare your measured g with the standard value (9.81 m/s²).
2. Discuss:
   - The effect of measurement resolution on Delta L.
   - Variability in timing and its impact on Delta T.
   - Any assumptions or experimental limitations.

## Deliverables
1. Present data:
   - L, Delta L, T10, T10 bar, Delta T.
   - Calculated g and Delta g.
2. The discussion on sources of uncertainty and their impact on the results.

## Example Data (Hypothetical)
- L = 1.50 m, Delta L = 0.001 m (ruler resolution 0.002 m).
- T10 measurements: [14.92, 14.88, 14.90, 14.91, 14.89, 14.93, 14.87, 14.90, 14.91, 14.88] s.
- T10 bar = 14.90 s, sigma T = 0.02 s.
- Delta T = 0.02 / square root of 10 ≈ 0.0063 s.
- T = 14.90 / 10 = 1.49 s, Delta T = 0.0063 / 10 ≈ 0.00063 s.
- g = 4 pi squared * 1.50 / 1.49 squared ≈ 9.83 m/s².
- Delta g = 9.83 [ (0.001 / 1.50) squared + (2 * 0.00063 / 1.49) squared ] to the power of 1/2 ≈ 0.02 m/s².

## Discussion
- Resolution Impact: The ruler's 0.002 m resolution limits Delta L, contributing minimally to Delta g.
- Timing Variability: Stopwatch precision affects Delta T, the dominant uncertainty source.
- Assumptions: Assumes small oscillations and negligible air resistance, which may slightly skew results.

![alt text](<Screenshot 2025-05-28 171042.png>)
![alt text](<Screenshot 2025-05-28 171048.png>)
Below is a Python script based on the task of measuring Earth's gravitational acceleration with a pendulum, incorporating the calculations and data analysis described earlier. The script includes hypothetical data, performs the necessary calculations, and visualizes the results using matplotlib.

```python
import numpy as np
import matplotlib.pyplot as plt

# Hypothetical data
L = 1.50  # Length of pendulum in meters
delta_L = 0.001  # Uncertainty in length (half resolution of 0.002 m ruler)
T10_measurements = [14.92, 14.88, 14.90, 14.91, 14.89, 14.93, 14.87, 14.90, 14.91, 14.88]  # Time for 10 oscillations in seconds
n = len(T10_measurements)  # Number of measurements

# Calculate mean and standard deviation of T10
T10_mean = np.mean(T10_measurements)
T10_std = np.std(T10_measurements, ddof=1)  # Sample standard deviation

# Calculate period T and its uncertainty
T = T10_mean / 10
delta_T = T10_std / np.sqrt(n) / 10  # Uncertainty propagated from T10

# Calculate gravitational acceleration g
g = 4 * np.pi**2 * L / T**2
# Propagate uncertainty in g
delta_g = g * np.sqrt((delta_L / L)**2 + (2 * delta_T / T)**2)

# Print results
print(f"Length (L): {L} ± {delta_L} m")
print(f"Mean time for 10 oscillations (T10): {T10_mean:.2f} ± {T10_std:.2f} s")
print(f"Period (T): {T:.2f} ± {delta_T:.2f} s")
print(f"Gravitational acceleration (g): {g:.2f} ± {delta_g:.2f} m/s²")

# Visualization
planets = ['Measured g', 'Standard g (9.81 m/s²)']
values = [g, 9.81]
errors = [delta_g, 0.0]  # No uncertainty for standard value

plt.figure(figsize=(8, 6))
plt.bar(planets, values, yerr=errors, capsize=5, color=['blue', 'green'])
plt.title('Measured vs Standard Gravitational Acceleration')
plt.ylabel('g (m/s²)')
plt.grid(True, linestyle='--', alpha=0.7)
plt.savefig('gravity_comparison.png')
plt.show()
```

### Explanation
- **Data**: Hypothetical values for pendulum length \( L \), its uncertainty \( \Delta L \), and 10 measurements of \( T_{10} \) are provided.
- **Calculations**:
  - Mean and standard deviation of \( T_{10} \) are computed.
  - Period \( T \) and its uncertainty \( \Delta T \) are derived.
  - Gravitational acceleration \( g \) is calculated using \( g = \frac{4\pi^2 L}{T^2} \), with uncertainty propagated as \( \Delta g = g \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2 \frac{\Delta T}{T}\right)^2} \).
- **Visualization**: A bar chart compares the measured \( g \) with the standard value (9.81 m/s²), including error bars for the measured value.
- **Output**: Results are printed, and a plot is saved as 'gravity_comparison.png'.
