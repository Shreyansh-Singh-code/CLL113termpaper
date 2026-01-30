

# Numerical Investigation of Laminar Boundary Layer with Wall Suction/Injection

**Course:** CLL113 – Numerical Methods in Chemical Engineering
**Institution:** Indian Institute of Technology Delhi
**Language:** C++
**Numerical Methods:** Shooting Method, Runge–Kutta 4 (RK4), Finite Difference Method (FDM)

---

## 📌 Project Overview

This project numerically investigates the **effect of wall suction and injection on a laminar boundary layer** by solving the **modified Blasius boundary value problem (BVP)**. The governing nonlinear ordinary differential equations are solved using two independent numerical approaches:

1. **Shooting Method combined with 4th-order Runge–Kutta (RK4)**
2. **Finite Difference Method (FDM)**

The results provide insight into how suction and injection influence velocity profiles, boundary layer thickness, and wall shear behavior.

---

## 🧠 Problem Formulation

The classical **Blasius equation** governing laminar boundary layer flow over a flat plate is modified to account for **wall suction/injection effects**. The resulting nonlinear BVP is transformed into a system of first-order ODEs:

[
\begin{aligned}
f' &= g \
g' &= h \
h' &= -\frac{1}{2} f h
\end{aligned}
]

with boundary conditions:

* At the wall: ( f(0) = 0 ), ( g(0) = S )
* At infinity: ( g(\infty) = 1 )

where **( S )** represents suction (( S < 0 )) or injection (( S > 0 )).

---

## 🔢 Numerical Methods Implemented

### 1️⃣ Shooting Method + RK4

* Converts the BVP into an Initial Value Problem (IVP)
* Iteratively guesses the unknown initial condition ( h(0) )
* Integrates the ODE system using **4th-order Runge–Kutta**
* Adjusts guesses until far-field boundary condition is satisfied

**Key features:**

* Explicit RK4 integration
* Parameter sweep over suction/injection values
* Convergence controlled via tolerance-based error checking

📂 **File:** `Shooting + RK-4.cpp`

---

### 2️⃣ Finite Difference Method (FDM)

* Discretizes the governing equations over a spatial grid
* Uses central difference approximations
* Solves the resulting nonlinear algebraic system iteratively

**Key features:**

* Stable spatial discretization
* Grid-based solution of BVP
* Independent validation of shooting method results

📂 **File:** `Shooting + FDM.cpp`

---

## 📊 Results & Observations

* **Wall suction** reduces boundary layer thickness and increases velocity gradient at the wall
* **Wall injection** thickens the boundary layer and delays velocity recovery
* Numerical results from **Shooting + RK4** closely match those from **FDM**, validating correctness
* Velocity profiles smoothly converge to free-stream conditions

Plots generated include:

* Velocity profiles for varying suction/injection parameters
* Comparative analysis between numerical methods

---

## 🛠️ Skills Demonstrated

* Numerical solution of **nonlinear boundary value problems**
* Implementation of **Runge–Kutta (RK4)** schemes
* Finite Difference discretization of ODEs
* Convergence analysis and error control
* Scientific computing in **C++**
* Physical interpretation of numerical fluid mechanics results

---

## 🚀 How to Run

```bash
g++ Shooting\ +\ RK-4.cpp -o shooting_rk4
./shooting_rk4

g++ Shooting\ +\ FDM.cpp -o shooting_fdm
./shooting_fdm
```

Output files contain velocity profiles suitable for plotting using Python, MATLAB, or GNUplot.

---

## 📚 References

* Blasius, H. (1908). *Grenzschichten in Flüssigkeiten mit kleiner Reibung*
* Schlichting, H. & Gersten, K. *Boundary-Layer Theory*
* Course notes: **CLL113 – IIT Delhi**

---
