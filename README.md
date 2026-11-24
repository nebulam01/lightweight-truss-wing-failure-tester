# Lightweight Truss Wing — 2D Failure & Buckling Tester

An interactive **Google Colab** engineering tool built with `ipywidgets`, `NumPy`, `Pandas`, and `Matplotlib` to design a lightweight 2D truss wing, evaluate axial member forces, and identify which members fail first—and why—under upward lift loading.

## Overview

Lightweight wing structures must resist bending and shear forces while minimizing structural mass. Using a 2D direct stiffness solver, this tool models a cantilever semi-span truss wing fixed at the root (`x = 0`) with upward aerodynamic lift distributed across spanwise stations, checking each member against **tensile yielding** and **compressive Euler buckling**.

### Supported Truss Patterns
- **Warren Truss**
- **Pratt Truss**
- **Howe Truss**

### Supported Materials
- **Balsa Wood (Medium)**
- **PLA (3D Print)**
- **Aluminum 6061-T6**
- **Carbon Fiber (UD)**

## Key Features

- **Interactive English UI (`ipywidgets`):** Configure truss pattern, material, semi-span, wing depth, number of bays, strut radius, and applied lift load, then run via the **Run 2D Truss Test** button.
- **2D Truss & Utilization Visualization:** Plots the 2D wing geometry with member utilization percentages (`%`) and highlights the first/most critical member with a dashed red line.
- **Member Force & Slenderness Table:** Displays axial force (`N`), allowable/buckling capacity (`N`), utilization (`%`), and slenderness ratio (`L/k`) for every chord, vertical, and diagonal member.
- **Failure & Root-Cause Explanation Card:** States whether structural failure occurs, identifies the first/most critical member, and explains the governing mechanism (such as Euler column buckling in slender compression members, slenderness effects, or tensile/root bending loads).

## How to Run in Google Colab

1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. Paste the truss wing tester code into a code cell and run it.
3. Adjust parameters, click **Run 2D Truss Test**, and inspect the 2D diagram, member table, and root-cause summary.

## Engineering Notes

- Compressive capacity accounts for slender strut Euler buckling alongside material yield limits, using pin-ended effective length ($K = 1.0$) and circular cross-section geometry.
- This educational/prototyping simulation supports conceptual structural trade-offs and should be paired with detailed FEA and physical load testing for flight hardware.
