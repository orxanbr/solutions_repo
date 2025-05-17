# Investigating the Range as a Function of the Angle of Projection

## 1. Theoretical Foundation

### Governing Equations of Motion

A projectile launched with an initial velocity $$v_0$$ at an angle $$\theta$$ from horizontal can be described using two motion components:

#### Horizontal motion (constant velocity):

$$
  x(t) = v_0 \cos(\theta) \cdot t
$$

#### Vertical motion (accelerated motion):

$$
  y(t) = h_0 + v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
$$

Where:  
- $$h_0$$: initial height  
- $$g$$: acceleration due to gravity (~9.81 m/s²)

Solving the vertical motion for $$y(t) = 0$$ gives the time of flight:

$$
  t = \frac{v_0 \sin(\theta) + \sqrt{(v_0 \sin(\theta))^2 + 2gh_0}}{g}
$$

### Horizontal Range

Using $$x(t) = v_0 \cos(\theta) \cdot t$$, the range becomes:

$$
  R = \frac{v_0 \cos(\theta)}{g} \left( v_0 \sin(\theta) + \sqrt{(v_0 \sin(\theta))^2 + 2gh_0} \right)
$$

If $$h_0 = 0$$:

$$
  R = \frac{v_0^2 \sin(2\theta)}{g}
$$