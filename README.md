# Numerical Methods – UCAECE

This repository contains implementations, theoretical notes, and numerical experiments developed for the course Numerical Methods, part of a postgraduate program at UCAECE.

The main goal is to apply mathematical and computational tools to approximate the solution of problems that do not have closed-form analytical solutions, with special emphasis on error analysis, stability, and convergence of numerical methods.

# Contents

This repository covers the following topics:

Numerical methods for solving nonlinear equations

Numerical methods for ordinary differential equations (ODEs)

Error and convergence analysis

Computational implementations and simulations

Visualization of numerical results

# Mathematical Problem

Many physical and engineering problems can be written in the form of an ordinary differential equation:

$$ \frac{dy}{dt} = f(t, y), \quad y(t_0) = y_0 $$

This equation describes how the variable $𝑦$ y changes with respect to time $𝑡$.
In most real-world cases, this equation cannot be solved analytically, so numerical methods are required.

## Implemented Numerical Methods
* Euler Method

The Euler method is the simplest numerical method to approximate the solution of an ODE.

$$y_{n+1} = y_n + h\,f(t_n, y_n)$$


Concept:

The solution is advanced step by step using the slope at the current point.

$h$ is the step size.

Easy to implement, but low accuracy and limited stability.

* Improved Euler Method (Heun)

This method improves Euler’s accuracy by averaging slopes:

$$y_{n+1} = y_n + \frac{h}{2}\left[f(t_n,y_n) + f(t_{n+1}, y_n + h f(t_n,y_n))\right]$$


Concept:

Uses a predictor–corrector idea.

Better accuracy than standard Euler.

Still simple and computationally efficient.

* Runge–Kutta Method (Fourth Order – RK4)

The RK4 method is one of the most widely used numerical methods for ODEs.

$$ k_1 = f(t_n, y_n)$$

$$ k_2 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_1\right)$$

$$ k_3 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_2\right)$$

$$ k_4 = f(t_n + h, y_n + h k_3)$$

$$ y_{n+1} = y_n + \frac{h}{6}(k_1 + 2k_2 + 2k_3 + k_4)$$


Concept:

Combines several slope evaluations to achieve high accuracy.

Fourth-order convergence.

Very good balance between precision and computational cost.

* Error and Convergence

The numerical error depends on the step size $ℎ$


Local truncation error:

$$\mathcal{O}(h^{p+1})$$


Global error:

$$\mathcal{O}(h^p)$$


where 

$p$ is the order of the numerical method.

Concept:

Smaller step size → higher accuracy.

Higher-order methods converge faster.


* Chebyshev Polynomials

Chebyshev polynomials are widely used in approximation theory and numerical interpolation due to their optimal properties in minimizing approximation error.

The Chebyshev polynomials of the first kind are defined as:

$$T_n(x) = \cos(n \cdot \arccos(x)), \quad x \in [-1,1]$$


They satisfy the recurrence relation:

$$T_{n+1}(x) = 2xT_n(x) - T_{n-1}(x)$$


Concept:

Used for polynomial approximation.

Reduce the Runge phenomenon.

Provide near-minimax optimal approximations.

* Lotka–Volterra Model

The Lotka–Volterra equations describe predator–prey dynamics and are a classical example of a nonlinear dynamical system.

$$\frac{dx}{dt} = \alpha x - \beta xy$$

$$ \frac{dy}{dt} = \delta xy - \gamma y $$

where:

$x(t)$ is the prey population

$y(t)$ is the predator population

$α$, $β$, $γ$, $δ$ are positive parameters

Concept:

## Nonlinear coupled ODE system.

Exhibits oscillatory behavior.

Often solved using numerical integration methods such as RK4.

* Simpson’s Rule (Numerical Integration)

Simpson’s rule is a numerical method for approximating definite integrals.

Given a function  $f(x)$ on the interval  $[a,b]$:

$$\int_a^b f(x)\,dx \approx \frac{h}{3}
\left[f(x_0) + 4f(x_1) + 2f(x_2) + \cdots + 4f(x_{n-1}) + f(x_n)\right]$$

where:

$$h = \frac{b-a}{n}, \quad n \text{ even}$$

Concept:

Uses quadratic interpolation.

Higher accuracy than the trapezoidal rule.

Error order $O(h^4)$.

* Finite Element Method (FEM)

The Finite Element Method is a numerical technique for solving partial differential equations (PDEs) by converting them into a variational problem.

A general boundary value problem can be written as:

$$-\nabla \cdot (k \nabla u) = f \quad \text{in } \Omega$$

The weak (variational) formulation is:

$$\int_\Omega k \nabla u \cdot \nabla v \, d\Omega
= \int_\Omega f v \, d\Omega$$

Concept:

The domain is divided into finite elements.

The solution is approximated using basis (shape) functions.

Widely used in engineering and physics simulations.
