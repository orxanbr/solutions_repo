# 🚀 Escape Velocities and Cosmic Velocities

## 📌 Motivation

Understanding the concept of **escape velocity** and the broader framework of **cosmic velocities** is essential for grasping how spacecraft travel within and beyond planetary systems. These velocities define the speed thresholds for different levels of orbital and escape maneuvers:

- Achieving orbit (1st Cosmic Velocity)  
- Escaping a planet's gravitational pull (2nd Cosmic Velocity)  
- Escaping a star system (3rd Cosmic Velocity)

These are key to:
- Launching and maintaining satellites  
- Planning interplanetary missions  
- Designing spacecraft capable of interstellar travel  

---

## 🌌 Definitions and Physical Meaning

### **First Cosmic Velocity** ($$v_1$$)

This is the **minimum horizontal velocity** an object must have to maintain a **stable circular orbit** just above the surface of a celestial body, assuming no atmospheric resistance.

$$
v_1 = \sqrt{\frac{GM}{R}}
$$

Where:  
- $G$ is the gravitational constant  
  $$
  G = 6.67430 \times 10^{-11} \ \text{m}^3 \ \text{kg}^{-1} \ \text{s}^{-2}
  $$  
- $M$ is the mass of the celestial body  
- $R$ is the radius from the center of mass (typically the planet's radius)  

### **Second Cosmic Velocity** 

Also known as **escape velocity**, this is the speed needed to **break free from the gravitational influence** of a planet or moon without further propulsion.

$$
v_2 = \sqrt{\frac{2GM}{R}} = \sqrt{2} \cdot v_1
$$

### **Third Cosmic Velocity** 

This is the speed required to escape **not just a planet, but the entire star system**. A probe must overcome the gravitational well of both the planet and the star.

A simplified estimate (assuming the object already escaped the planet and is in a solar orbit):

$$
v_3 \approx \sqrt{2} \cdot v_2 = 2 \cdot v_1
$$

---

## 🧮 Mathematical Derivation

### Derivation of Escape Velocity (2nd Cosmic Velocity):

From energy conservation:

- Initial total energy:  
  $$
  E_i = \frac{1}{2}mv^2 - \frac{GMm}{R}
  $$
- Final total energy at infinity:  
  $$
  E_f = 0
  $$

Setting $$E_i = E_f$$:

$$
\frac{1}{2}mv^2 = \frac{GMm}{R} \Rightarrow v = \sqrt{\frac{2GM}{R}}
$$

This equation underpins both $$v_2$$ and, indirectly, $$v_3$$.

---

## 🌍 Calculated Cosmic Velocities for Earth, Mars, and Jupiter

### Parameters Used:

| Body    | Mass (kg)            | Radius (m)           |
|---------|----------------------|----------------------|
| Earth   | 5.972 × 10²⁴         | 6.371 × 10⁶          |
| Mars    | 6.39 × 10²³          | 3.3895 × 10⁶         |
| Jupiter | 1.898 × 10²⁷         | 6.9911 × 10⁷         |

### Results:

| Body    | $$v_1$$ (km/s) | $$v_2$$ (km/s) | $$v_3$$ (km/s) |
|---------|----------------|----------------|----------------|
| Earth   | 7.91           | 11.19          | 15.82          |
| Mars    | 3.55           | 5.02           | 7.09           |
| Jupiter | 42.57          | 60.20          | 85.14          |

---

## 📊 Visual Representation

> Add this image manually or run the code below to generate a bar chart for:
> - 1st Cosmic Velocity: Orbital Insertion  
> - 2nd Cosmic Velocity: Planetary Escape  
> - 3rd Cosmic Velocity: Interstellar Escape  

---

## 🚀 Applications in Space Exploration

| Mission Objective                     | Required Velocity |
|--------------------------------------|--------------------|
| Satellite Deployment (LEO, MEO, GEO) | 1st Cosmic         |
| Interplanetary Probes                | 2nd Cosmic         |
| Interstellar Probes                  | 3rd Cosmic         |

### Examples

- **1st Cosmic**: Starlink orbits via Falcon 9  
- **2nd Cosmic**: Mars Rover missions  
- **3rd Cosmic**: Voyager 1 and 2 leaving solar system  

---

## 📍 Real-World Considerations

- **Atmospheric Drag**: Neglected in ideal model  
- **Launch Profiles**: Real missions use staged rockets  
- **Gravitational Assists**: Reduce $$\Delta v$$ for $$v_3$$  
- **Oberth Effect**: Velocity burns more effective deeper in gravity well  

---

## 🔎 Further Exploration

- Explore slingshot maneuvers  
- Add Moon, Titan, Europa to table  
- Simulate velocity vs altitude  
- Model delta-v requirements for entire mission stacks  

---

## 🔢 Python Simulation Code

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # Gravitational constant in m^3 kg^-1 s^-2

# Planetary data
bodies = {
    "Earth":   {"mass": 5.972e24,  "radius": 6.371e6},
    "Mars":    {"mass": 6.39e23,   "radius": 3.3895e6},
    "Jupiter": {"mass": 1.898e27,  "radius": 6.9911e7}
}

# Velocity calculation
def calculate_cosmic_velocities(m, r):
    v1 = np.sqrt(G * m / r)
    v2 = np.sqrt(2) * v1
    v3 = np.sqrt(2) * v2
    return v1, v2, v3

results = {}
for name, props in bodies.items():
    v1, v2, v3 = calculate_cosmic_velocities(props["mass"], props["radius"])
    results[name] = [v1/1000, v2/1000, v3/1000]  # Convert to km/s

# Plotting
labels = list(results.keys())
v1_vals = [results[k][0] for k in labels]
v2_vals = [results[k][1] for k in labels]
v3_vals = [results[k][2] for k in labels]

x = np.arange(len(labels))
width = 0.25

plt.figure(figsize=(10,6))
plt.bar(x - width, v1_vals, width, label='1st Cosmic Velocity')
plt.bar(x,         v2_vals, width, label='2nd Cosmic Velocity')
plt.bar(x + width, v3_vals, width, label='3rd Cosmic Velocity')

plt.xticks(x, labels)
plt.ylabel('Velocity (km/s)')
plt.title('Cosmic Velocities for Celestial Bodies')
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```

---

## ✋ Conclusion

The cosmic velocity framework provides a conceptual and mathematical foundation for space exploration. Whether launching a satellite, sending a rover to Mars, or dreaming of reaching another star, these velocity thresholds set the minimum physical limits that technology must overcome.

Understanding them deepens our appreciation of the challenges and brilliance behind modern rocketry and spacecraft engineering.
