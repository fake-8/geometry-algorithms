# Computer Graphics: Geometry Drawing Algorithms
### CPS Minor Project | Course: ME2339E

This repository contains Python-based implementations of fundamental scan-conversion algorithms. These are essential in **Cyber-Physical Systems** for rendering digital models onto raster displays using computationally efficient, integer-only arithmetic.

# Algorithms Implemented

### 1. Bresenham's Line Drawing Algorithm (LDA)
An efficient algorithm used to determine the points of a raster that form a close approximation to a straight line.
* Logic: Uses a decision parameter Pk to choose the next pixel without floating-point division.
* Decision Parameter:
    * #for dx>dy
          *initial parameter,P0=2*dy-dx
          *if Pk<0:Pk=Pk+2*dy
          *if Pk>=0:Pk=2*dy-2*dx+Pk
    * #for dx<dy
          *initial parameter,P0=2*dx-dy
          *if Pk<0:Pk=Pk+2*dx
          *if Pk>=0:Pk=2*dx-2*dy+Pk
### 2. Midpoint Circle Drawing Algorithm
This algorithm calculates the coordinates for one octant ($45^\circ$) and uses 8-way symmetry to complete the circle, significantly reducing computational load.
* Logic: Minimizes computation by avoiding trigonometric functions (sine,cosine,etc).
* Decision Parameter:
   * For second_octant
      initial parameter,P0=1-radius
      if Pk<0:  #y increment =0
           Pk=Pk+2*x+1  
      if Pk>=0: #y increment =-1
           Pk = Pk + 2 * (x - y) + 1
* Symmetry Implementation:
    * For first octant we just interchange the x and y cordinates
    * Fot the first half circle we add the same cordinate with negated x-axis
    * For Full circle we add the cordinates of the first half with negating the y-axis 
##  Visualizations
The algorithms are implemented in Jupyter Notebooks (`.ipynb`) using `Matplotlib` to visualize the pixel-by-pixel generation of the geometric shapes.

---
Author: Mohammad Hashim R 
Institution: NIT Calicut  
Department: Electronics and Communication Engineering
