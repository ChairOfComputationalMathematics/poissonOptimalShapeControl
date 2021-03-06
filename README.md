# Optimal Shape Design for Poisson Equation in Matlab

We study the shape design problem through the minimization of the cost functional

<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?%5Cmathcal%7BJ%7D%20%5Cleft%28%20%5Ctheta%2C%20y%20%5Cright%29%20%3D%20%5Cfrac%7B1%7D%7B2%7D%20%5Cint_%7B%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%7D%20%5Cleft%28%20y%20-%20y_d%20%5Cright%29%20%5E2%20%5C%2C%20%5Cmathrm%7Bd%7D%20%5COmega%2C">
</p>

where <img src="https://latex.codecogs.com/gif.latex?y%20%5Cin%20L%5E2%20%5Cleft%28%20%5COmega%20%5Cright%29"> is the state variable, <img src="https://latex.codecogs.com/gif.latex?y_d%20%5Cin%20L%5E2%20%5Cleft%28%20%5COmega%20%5Cright%29"> is a target function, and <img src="https://latex.codecogs.com/gif.latex?%5Ctheta%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29"> the normal displacement to a reference boundary,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5CGamma%20%5Cleft%28%20%5Ctheta%20%5Cright%29%20%3D%20%5Cleft%5C%7B%20%5Cmathbf%7Bx%7D%20&plus;%20%5Ctheta%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%20%5Cmathbf%7Bn%7D%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%20%3A%20%5Cmathbf%7Bx%7D%20%5Cin%20%5CGamma_%7B0%7D%20%5Cright%5C%7D.">
</p>

The problem is subject to the following elliptic PDE in the domain <img src="https://latex.codecogs.com/gif.latex?%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%20%5Csubset%20%5Cmathbb%7BR%7D%5Ed"> with Dirichlet boundary conditions on <img src="https://latex.codecogs.com/gif.latex?%5CGamma%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%20%3D%20%5CGamma_w%20%5Ccup%20%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29">,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Bcases%7D%20-%5CDelta%20y%20%3D%20f%20%26%20%5Ctext%7Bin%20%7D%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%2C%5C%5C%20y%20%3D%20y_%7Bw%7D%20%26%20%5Ctext%7Bin%20%7D%20%5CGamma_w%2C%5C%5C%20y%20%3D%20y_%7Bs%7D%20%26%20%5Ctext%7Bin%20%7D%20%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%2C%20%5Cend%7Bcases%7D">
</p>

and <img src="https://latex.codecogs.com/gif.latex?f%20%5Cin%20L%5E2%20%5Cleft%28%20%5COmega%20%5Cright%29">.

We consider the set of admissible domains whose measure is fixed,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathcal%7BU%7D_%7Bad%7D%20%3D%20%5Cleft%5C%7B%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%20%3A%20%5Clvert%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%20%5Crvert%20%3D%20%5COmega_0%20%5Cright%5C%7D%2C">
</p>

and aim at finding the optimal shape that minimizes the cost function. In order to do so, we use the steepest descent method with descent direction given by

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cdelta%20%5Ctheta%20%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20%3D%20-%20%5Cleft%5B%20%5Cfrac%7B1%7D%7B2%7D%20%5Cleft%28%20y%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20-%20y_d%20%5Cright%29%20%5E2%20&plus;%20%5Cfrac%7B%5Cpartial%20v%7D%7B%5Cpartial%20n%7D%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20%5Cfrac%7B%5Cpartial%20y%7D%7B%5Cpartial%20n%7D%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20&plus;%20q%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20%5Cright%5D%2C">
</p>

where <img src="https://latex.codecogs.com/gif.latex?v"> is solution of the adjoint problem

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Bcases%7D%20-%20%5CDelta%20v%20%3D%20y%20-%20y_d%20%26%20%5Ctext%7Bin%20%7D%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%2C%20%5C%5C%20v%20%3D%200%20%26%20%5Ctext%7Bon%20%7D%20%5CGamma%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%20%3D%20%5CGamma_w%20%5Ccup%20%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29.%20%5Cend%7Bcases%7D">
</p>

The normal displacement field is updated at every iteration,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Ctheta%5E%7B%5Cleft%28%20n%20&plus;%201%20%5Cright%29%7D%20%3D%20%5Ctheta%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20&plus;%20%5Cepsilon%20%5Cdelta%7B%5Ctheta%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%7D%2C">
</p>

with <img src="https://latex.codecogs.com/gif.latex?\epsilon"> sufficiently small. The Lagrange multiplier is computed in order to ensure that the volume contraint is fulfilled, thus

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?q%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20%3D%20-%20%5Cfrac%7B1%7D%7B%5Cleft%7C%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%5Cright%7C%7D%20%5Cint_%7B%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%7D%20%5Cleft%5B%20%5Cfrac%7B1%7D%7B2%7D%20%5Cleft%28%20y%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20-%20y_d%20%5Cright%29%20%5E2%20&plus;%20%5Cfrac%7B%5Cpartial%20v%7D%7B%5Cpartial%20n%7D%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20%5Cfrac%7B%5Cpartial%20y%7D%7B%5Cpartial%20n%7D%5E%7B%5Cleft%28%20n%20%5Cright%29%7D%20%5Cright%5D%20%5Cmathrm%7Bd%7D%20%5CGamma.">
</p>

## Mesh Motion Solver

The solutions to the primal and adjoint problems are commonly approximated by means of numerical methods, such as the finite element method (FEM) or the finite volume method (FVM). In order to apply these techniques, the domain under study must be tessellated with a mesh. Nevertheless, applying the displacement directly to the controlled boundary will deteriorate the surrounding elements after a few iterations and the computation will crash if the interior nodes of the domain are not reallocated. In order to avoid this, the domain can be re-meshed after a number of iterations. However, this can be very expensive as a completely new mesh must be generated. A commonly used alternative is to move the interior nodes of the mesh according to the displacements prescribed on the boundary.  By doing this the number of elements and the nodes connectivities remain the same, only the mesh nodes positions are updated.

### Linear Elasticity

Mesh motion can be achieved by treating the mesh as an elastic body and solving the equations of Linear Elasticity for solids with prescribed displacements on the domain boundary,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Bcases%7D%20%5Cpartial_j%20%5Cleft%28%20G%20%5Cpartial_j%20u_i%20%5Cright%29%20&plus;%20%5Cpartial_j%20%5Cleft%28%20G%20%5Cpartial_i%20u_j%20%5Cright%29%20&plus;%20%5Cpartial_i%20%5Cleft%28%20%5Clambda%20%5Cpartial_j%20u_j%20%5Cright%29%20%3D%200%20%26%20%5Ctext%7Bin%20%7D%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%2C%20%5C%5C%20u_i%20%3D%200%20%26%20%5Ctext%7Bon%20%7D%20%5CGamma_w%2C%20%5C%5C%20u_i%20%3D%20%5Cdelta%20%5Ctheta%20n_i%20%26%20%5Ctext%7Bon%20%7D%20%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29.%20%5Cend%7Bcases%7D">
</p>

### Solid Body Rotation (SBR) Stress

The Linear Elasticity model fails when dealing with rotating meshes. This can be mitigated by selecting the material properties in a proper manner, which yields

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Bcases%7D%202%20%5Cpartial_j%20%5Cleft%28%20%5Cgamma%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%20%5Cpartial_j%20u_i%20%5Cright%29%20&plus;%20%5Cpartial_j%20%5Cleft%5B%20%5Cgamma%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%20%5Cleft%28%20%5Cpartial_i%20u_j%20-%20%5Cpartial_j%20u_i%20-%20%5Cdelta_%7Bij%7D%20%5Cpartial_k%20u_k%20%5Cright%29%20%5Cright%5D%20%3D%200%2C%20%26%20%5Ctext%7Bin%20%7D%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%2C%20%5C%5C%20u_i%20%3D%200%20%26%20%5Ctext%7Bon%20%7D%20%5CGamma_w%2C%20%5C%5C%20u_i%20%3D%20%5Cdelta%20%5Ctheta%20n_i%20%26%20%5Ctext%7Bon%20%7D%20%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29.%20%5Cend%7Bcases%7D">
</p>

### Laplacian Smoothing

A simple and widely used practice is to solve a Laplace equation with the prescribed displacements as boundary conditions,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Bcases%7D%20%5CDelta%20u_i%20%3D%200%20%26%20%5Ctext%7Bin%20%7D%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%2C%20%5C%5C%20u_i%20%3D%200%20%26%20%5Ctext%7Bon%20%7D%20%5CGamma_w%2C%20%5C%5C%20u_i%20%3D%20%5Cdelta%20%5Ctheta%20n_i%20%26%20%5Ctext%7Bon%20%7D%20%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29.%20%5Cend%7Bcases%7D">
</p>

The behavior of the Laplacian smoothing can be improved by adding a non-uniform diffusivity term,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cpartial_k%20%5Cleft%28%20%5Cgamma%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%20%5Cpartial_k%20u_i%20%5Cright%29%20%3D%200%20%5Cquad%20%5Ctext%7Bin%20%7D%20%5COmega%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29.">
</p>

The diffusion field <img src="https://latex.codecogs.com/gif.latex?%5Cgamma%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%3A%20%5Cmathbb%7BR%7D%5Ed%20%5Crightarrow%20%5Cmathbb%7BR%7D"> decreases with the distance to the controlled boundary. A common choice is to make it depend on the inverse of the distance as

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cgamma%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%20%3D%20%5Cfrac%7B1%7D%7Bd%5Em%7D%2C">
</p>

so that the nodes next to the deforming boundaries move with similar displacements as those on the boundary.

### Spring Analogy

A more intuitive approach is reached by thinking of the N mesh nodes as a mechanical system consisting of a finite set of masses that are linked with springs along the mesh edges. We can consider the existence of additional external forces acting on every mesh node, so that for every equilibrium configuration the following must hold,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7BF%7D_i%20-%20%5Csum_%7Bj%3D1%7D%5EN%20k_%7Bij%7D%20%5Cleft%28%20%5Cmathbf%7Bx%7D_i%20-%20%5Cmathbf%7Bx%7D_j%20%5Cright%29%20%3D%200%2C%20%5Cquad%201%20%5Cleq%20i%20%5Cleq%20N.">
</p>

The equilibrium equations can be expressed in terms of the nodes displacements,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7B%5CDelta%20F%7D_i%20-%20%5Csum_%7Bj%3D1%7D%5EN%20k_%7Bij%7D%20%5Cleft%28%20%5Cmathbf%7Bu%7D_i%20-%20%5Cmathbf%7Bu%7D_j%20%5Cright%29%20%3D%200%2C%20%5Cquad%201%20%5Cleq%20i%20%5Cleq%20N.">
</p>

At the M nodes that belong to the domain boundary the displacements are prescribed with unknown forces acting on them. On the other hand, on the interior nodes of the mesh whose displacements are unknown, there are no other forces than the elastic ones. Let us denote with D the indices of the nodes with prescribed displacement, and with S the set of nodes with unknown displacements. The equilibrium can be expressed in matrix form as

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Balign*%7D%20%5Cmathbf%7BK%7D_%7BDD%7D%20%5Cmathbf%7Bu%7D_D%20&plus;%20%5Cmathbf%7BK%7D_%7BDS%7D%20%5Cmathbf%7Bu%7D_%7BS%7D%20%26%20%3D%20%5Cmathbf%7B%5CDelta%20F%7D_%7BD%7D%2C%20%5C%5C%20%5Cmathbf%7BK%7D_%7BSD%7D%20%5Cmathbf%7Bu%7D_D%20&plus;%20%5Cmathbf%7BK%7D_%7BSS%7D%20%5Cmathbf%7Bu%7D_%7BS%7D%20%26%20%3D%20%5Cmathbf%7B%5CDelta%20F%7D_%7BS%7D%20%3D%20%5Cmathbf%7B0%7D.%20%5Cend%7Balign*%7D">
</p>

One can get the displacements of the interior mesh nodes as

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7Bu%7D_S%20%3D%20-%5Cmathbf%7BK%7D_%7BSS%7D%5E%7B-1%7D%20%5Cmathbf%7BK%7D_%7BSD%7D%20%5Cmathbf%7Bu%7D_D.">
</p>

### Radial Basis Functions (RBF)

The RBF mesh morphing technique uses the known displacements at the domain boundaries to construct an interpolation expression as a weighted sum of radial functions <img src="https://latex.codecogs.com/gif.latex?%5Cvarphi%3A%20%5Cmathbb%7BR%7D%20%5Crightarrow%20%5Cmathbb%7BR%7D">,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?s%5E%7B%5Calpha%7D%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%20%3D%20%5Csum_%7Bj%3D1%7D%5EN%20%5Cgamma%5E%7B%5Calpha%7D_j%20%5Cvarphi%20%5Cleft%28%20%5C%7C%20%5Cmathbf%7Bx%7D%20-%20%5Cmathbf%7Bx%7D_%7Bs%2C%20j%7D%20%5C%7C_%7B%5Cmathbb%7BR%7D%5Ed%7D%20%5Cright%29%20&plus;%20p%5E%7B%5Calpha%7D%20%5Cleft%28%20%5Cmathbf%7Bx%7D%20%5Cright%29%2C%20%5Cquad%201%20%5Cleq%20%5Calpha%20%5Cleq%20d.">
</p>

The weighting coefficients and the polynomials are obtained by imposing the known displacements at the boundaries,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?s%5E%7B%5Calpha%7D%20%5Cleft%28%20%5Cmathbf%7Bx%7D_%7Bs%2C%20i%7D%20%5Cright%29%20%3D%20g%5E%7B%5Calpha%7D_%7Bs%2C%20i%7D%20%3D%20%5Cdelta%20%5Ctheta%20n%5E%7B%5Calpha%7D%2C">
</p>

and the orthogonality conditions for every polynomial with degree less or equal than that of <img src="https://latex.codecogs.com/gif.latex?p%5E%7B%5Calpha%7D">,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Csum_%7Bj%3D1%7D%5EN%20%5Cgamma%5E%7B%5Calpha%7D_j%20q%20%5Cleft%28%20%5Cmathbf%7Bx%7D_%7Bs%2Cj%7D%20%5Cright%29%20%3D%200%2C%20%5Cquad%201%20%5Cleq%20%5Calpha%20%5Cleq%20d.">
</p>

At the end, a linear system of the form

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Bpmatrix%7D%20%5Cmathbf%7BM%7D_s%20%26%20%5Cmathbf%7BP%7D_s%20%5C%5C%20%5Cmathbf%7BP%7D_s%5ET%20%26%20%5Cmathbf%7B0%7D%20%5Cend%7Bpmatrix%7D%20%5Cbegin%7Bpmatrix%7D%20%5Cmathbf%7B%5Cgamma%7D%5E%7B%5Calpha%7D%20%5C%5C%20%5Cmathbf%7B%5Cbeta%7D%5E%7B%5Calpha%7D%20%5Cend%7Bpmatrix%7D%20%3D%20%5Cbegin%7Bpmatrix%7D%20%5Cmathbf%7Bg%7D_s%5E%7B%5Calpha%7D%20%5C%5C%20%5Cmathbf%7B0%7D%20%5Cend%7Bpmatrix%7D">
</p>

must be solved, and the mesh nodes are updated as

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?x%5E%7B%5Cmathrm%7Bnew%7D%2C%20%5Calpha%7D%20%3D%20x%5E%7B%5Cmathrm%7Bold%7D%2C%20%5Calpha%7D%20&plus;%20s%5E%7B%5Calpha%7D%5Cleft%28%20%5Cmathbf%7Bx%7D%5E%7B%5Cmathrm%7Bold%7D%7D%20%5Cright%29.">
</p>

### Free Form Deformation (FFD)

An alternative is to use some parametrization technique for the boundary <img src="https://latex.codecogs.com/gif.latex?%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29"> and extend it to be able to handle the motion of the interior nodes of the mesh as well. This can be done with the Free Form Deformation method, that is based upon the positions of a set of control points inside a parallelepiped.

If we consider the 2-dimensional reference control domain <img src="https://latex.codecogs.com/gif.latex?%5COmega_%7Bst%7D%3D%5Cleft%5B%200%2C%201%20%5Cright%5D%20%5Ctimes%20%5Cleft%5B%200%20%2C%201%20%5Cright%5D">, we can define a set of <img src="https://latex.codecogs.com/gif.latex?%5Cleft%28%20N%20&plus;%201%20%5Cright%29%20%5Ctimes%20%5Cleft%28%20M%20&plus;%201%20%5Cright%29"> evenly spaced control points,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7BP%7D_%7Bij%7D%20%3D%20%5Cleft%28%20%5Cfrac%7Bi%7D%7BM%7D%2C%20%5Cfrac%7Bj%7D%7BN%7D%20%5Cright%29%2C%20%5Cquad%200%20%5Cleq%20i%20%5Cleq%20M%2C%20%5Cquad%200%20%5Cleq%20j%20%5Cleq%20N%2C">
</p>

and introduce the tensorial product of Bernstein polynomials <img src="https://latex.codecogs.com/gif.latex?B_%7Bij%7D%5E%7BMN%7D%5Cleft%5B%5Cmathbf%7BS%7D%20%3D%20%5Cleft%28s%2C%20t%20%5Cright%29%20%5Cright%5D%20%3D%20b_i%20%5EM%20%5Cleft%28%20s%20%5Cright%29%20b_j%20%5EN%20%5Cleft%28%20t%20%5Cright%29">, with

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Balign*%7D%20b_i%5EM%20%5Cleft%28%20s%20%5Cright%29%20%26%3D%20%5Cbinom%7BM%7D%7Bi%7D%20s%5Ei%20%5Cleft%281-s%5Cright%29%20%5E%7BM-i%7D%2C%20%5C%5C%20b_j%5EN%20%5Cleft%28%20t%20%5Cright%29%20%26%3D%20%5Cbinom%7BN%7D%7Bj%7D%20t%5Ej%20%5Cleft%281-t%5Cright%29%20%5E%7BN-j%7D.%20%5Cend%7Balign*%7D">
</p>

The transformation

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7B%5CPsi%7D%20%5Cleft%28%20%5Cmathbf%7BS%7D%20%5Cright%29%20%3D%20%5Csum_%7Bi%3D0%7D%5EM%20%5Csum_%7Bj%3D0%7D%5EN%20B_%7Bij%7D%5E%7BMN%7D%20%5Cleft%28%20%5Cmathbf%7BS%7D%20%5Cright%29%20%5Cmathbf%7BP%7D_%7Bij%7D">
</p>

is the identity transformation, i.e., <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7B%5CPsi%7D%5Cleft%28%20%5Cmathbf%7BS%7D%20%5Cright%29%20%3D%20%5Cmathbf%7BS%7D">. 

We consider a set of control points defined as displacements from the reference positions, <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7BP%7D_%7Bij%7D%20&plus;%20%5Cmathbf%7B%5CDelta%20P%7D_%7Bij%7D">. In this case it is easy to see that the following holds

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7B%20%5CDelta%20S%20%7D%20%3D%20%5Cmathbf%7B%20%5CPsi%20%7D%20%5Cleft%28%20%5Cmathbf%7BS%7D%20%5Cright%29%20-%20%5Cmathbf%7BS%7D%20%3D%20%5Csum_%7Bi%3D0%7D%5EM%20%5Csum_%7Bj%3D0%7D%5EN%20B_%7Bij%7D%5E%7BMN%7D%20%5Cleft%28%20%5Cmathbf%7BS%7D%20%5Cright%29%20%5Cmathbf%7B%20%5CDelta%20P%20%7D_%7Bij%7D.">
</p>

We must find the control points displacements <img src="https://latex.codecogs.com/gif.latex?%24%5Cmathbf%7B%5CDelta%20P%7D_%7Bij%7D%20%5Cin%20%5COmega_%7Bst%7D%24"> that parametrize the controlled boundary and for which, for every boundary node <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7BX%7D_%7Bs%2Ck%7D%20%5Cin%20%5CGamma_s%20%5Cleft%28%20%5Ctheta%20%5Cright%20%29%2C%20%5C%201%20%5Cleq%20k%20%5Cleq%20Z">,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7B%5CPhi%7D%20%5Cleft%28%20%5Cmathbf%7BX%7D_%7Bs%2Ck%7D%20&plus;%20%5Cvar%7B%5Ctheta%7D%20%5Cmathbf%7Bn%7D%20%5Cright%29%20-%20%5Cmathbf%7B%5CPhi%7D%20%5Cleft%28%20%5Cmathbf%7BX%7D_%7Bs%2Ck%7D%20%5Cright%29%20%3D%20%5Csum_%7Bi%3D0%7D%5EM%20%5Csum_%7Bj%3D0%7D%5EN%20B_%7Bij%7D%5E%7BMN%7D%20%5Cleft%5B%20%5Cmathbf%7B%5CPhi%7D%20%5Cleft%28%20%5Cmathbf%7BX%7D_%7Bs%2Ck%7D%20%5Cright%29%20%5Cright%5D%20%5Cmathbf%7B%20%5CDelta%20P%7D_%7Bij%7D%2C%20%5Cquad%201%20%5Cleq%20k%20%5Cleq%20M.">
</p>

## Getting Started

The file _main.m_ needs to be run from the Matlab command line,

```Matlab
main.m
```

### Dynamic Mesh

The different mesh motion methods can be selected in the heading of _main.m_

```Matlab
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% PARAMETERS
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Minimum element size
Hmin = 1e-3;
% Maximum elements size
Hmax = 0.05;
% Step theta^{n+1} = theta^{n} - d * Dtheta^{n}
d = 1e-3;
% Maximum number of iterations
maxIter = 2000000;
% Dirichlet boundary condition on the outer boundary
ue = 1;
% Dirichlet boundary condition on the inner boundary
uc = 0;
% Smoothing of sensitivity field
smoothing = true;
% Reshaping of elements whose edges are lying on the controlled boundary
reshaping = true;
% Mesh motion solver method:
% - Laplace Equation ('laplace')
% - Spring Analogy ('spring')
% - Free Form Deformation ('FFD')
% - Radial Basis Functions ('RBF')
meshMotionSolver = 'laplace';
% Parameters for Laplace method
% Diffusivity (diff)
% - Inverse distance ('invdist')
invdist = true;
m = 6;
% Parameters for FFD method:
% Mi - number of control points along X axis
% Nj - number of control points along Y axis
% Xmin, Xmax - coordinates defining the control rectangle
Mi = 9;
Nj = 9;
Xmin = [-0.7, -0.6];
Xmax = -Xmin;
% Parameters for RBF method
% h - Dimensionless radial distance (r/h)
% RBFtype - Radial Basis Functions
% - Spline type, n odd ('Rn')
% - Thin Plate Spline, n even ('TPSn')
% - Multiquadratic ('MQ')
% - Inverse multiquadratic ('IMQ')
% - Inverse quadratic ('IQ')
% - Gaussian ('GS')
% n - Exponent
h = 2.5*0.3;
RBFtype = 'R';
n = 1;
```

## Running a Case

The shape optimization method described in the previous section has been tested with a simple example. The Poisson equation is posed in a two-dimensional circular domain with boundary

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5CGamma_w%20%3D%20%5Cleft%5C%7B%20%5Cleft%28%20x%2C%20y%20%5Cright%29%20%5Cin%20%5Cmathbb%7BR%7D%5E2%3A%20%5Csqrt%7Bx%5E2%20&plus;%20y%5E2%7D%20%3D%20R_w%20%5Cright%5C%7D.">
</p>

The reference geometry to be optimized is an inner hole with boundary given by

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5CGamma_s%20%5Cleft%28%200%5Cright%29%20%3D%20%5Cleft%5C%7B%20%5Cleft%28%20x%2C%20y%20%5Cright%29%20%5Cin%20%5Cmathbb%7BR%7D%5E2%20%3A%20%5Csqrt%7B%5Cleft%28%20x%20-%20c_x%20%5Cright%29%5E2%20&plus;%20%5Cleft%28%20y%20-%20c_y%20%5Cright%29%5E2%7D%20%3D%20R_s%20%5Cright%5C%7D.">
</p>

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig1.png" target="_blank"><img src="figs/fig1.png" width="400" height="340"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig1.png" target="_blank">Click here to open image 1.</a>
</p>

The target function <img src="https://latex.codecogs.com/gif.latex?u_d"> will be the analytical solution of the Poisson equation with the inner hole centered in the origin,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?u_%7Banalytic%7D%5Cleft%28%20r%20%5Cright%29%20%3D%20-%5Cfrac%7Bf%7D%7B4%7Dr%5E2%20&plus;%20c_1%20%5Clog%20r%20&plus;%20c_2%2C">
</p>

where the integration constants are obtained from the boundary conditions,

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5Cbegin%7Balign*%7D%20c_1%20%3D%20%26%20%5Cfrac%7Bu_w%20-%20u_s%20&plus;%20%5Cdisplaystyle%20%5Cfrac%7Bf%7D%7B4%7D%20%5Cleft%28%20R_w%5E2%20-%20R_s%5E2%20%5Cright%29%7D%7B%5Clog%5Cleft%28%20%5Cdisplaystyle%20%5Cfrac%7BR_w%7D%7BR_s%7D%20%5Cright%29%7D%2C%20%5C%5C%20c_2%20%3D%20%26%20%5Cfrac%7Bu_w%20&plus;%20u_s%7D%7B2%7D%20&plus;%20%5Cfrac%7Bf%7D%7B8%7D%5Cleft%28%20R_w%5E2%20&plus;%20R_s%5E2%20%5Cright%29%20-%20%5Cfrac%7Bc_1%7D%7B2%7D%20%5Clog%5Cleft%28%20R_w%20R_s%20%5Cright%29.%20%5Cend%7Balign*%7D">
</p>

When the hole center is displaced from the origin, the target state must be extended in the region <img src="https://latex.codecogs.com/gif.latex?r%20%5Cleq%20R_1">, thus

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?u_d%5Cleft%28%20r%20%5Cright%29%3D%20%5Cbegin%7Bcases%7D%20u_s%2C%20%5Cquad%20%26%20r%20%5Cleq%20R_s%2C%20%5C%5C%20u_%7Banalytic%7D%2C%20%5Cquad%20%26%20R_s%20%3C%20r%20%5Cleq%20R_w.%20%5Cend%7Bcases%7D">
</p>

It is clear that for

<p align="center">
    <img src="https://latex.codecogs.com/gif.latex?%5CGamma%5E%7B*%7D_s%20%3D%20%5Cleft%5C%7B%20%5Cleft%28%20x%2C%20y%20%5Cright%29%20%5Cin%20%5Cmathbb%7BR%7D%5E2%20%3A%20%5Csqrt%7Bx%5E2%20&plus;%20y%5E2%7D%20%3D%20R_s%20%5Cright%5C%7D">
</p>

the cost function equals zero, thus it is an optimal solution. The steepest descent algorithm has been coded in Matlab with <img src="https://latex.codecogs.com/gif.latex?%5Cepsilon%20%3D%2010%5E%7B-3%7D">.

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig2.png" target="_blank"><img src="figs/fig2.png" width="400" height="300"></a>
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig3.png" target="_blank"><img src="figs/fig3.png" width="400" height="300"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig2.png" target="_blank">Click here to open image 2.</a>
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig3.png" target="_blank">Click here to open image 3.</a>
</p>

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/laplace_c1_NS_NR_invdist2.gif" target="_blank"><img src="figs/laplace_c1_NS_NR_invdist2.gif" width="400" height="300"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/laplace_c1_NS_NR_invdist2.gif" target="_blank">Click here to open animation 1.</a>
</p>

Other geometry configurations have been tried. For instance, the inner hole can be initially located farther from its optimal position,

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig4.png" target="_blank"><img src="figs/fig4.png" width="400" height="340"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig4.png" target="_blank">Click here to open image 4.</a>
</p>

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig5.png" target="_blank"><img src="figs/fig5.png" width="400" height="300"></a>
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig6.png" target="_blank"><img src="figs/fig6.png" width="400" height="300"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig5.png" target="_blank">Click here to open image 5.</a>
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig6.png" target="_blank">Click here to open image 6.</a>
</p>

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/laplace_c3_S_R_invdist2.gif" target="_blank"><img src="figs/laplace_c1_NS_NR_invdist2.gif" width="400" height="300"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/laplace_c3_S_R_invdist2.gif" target="_blank">Click here to open animation 2.</a>
</p>

Different starting shapes can be tested as well,

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig7.png" target="_blank"><img src="figs/fig7.png" width="400" height="340"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig7.png" target="_blank">Click here to open image 7.</a>
</p>

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig8.png" target="_blank"><img src="figs/fig8.png" width="400" height="300"></a>
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig9.png" target="_blank"><img src="figs/fig9.png" width="400" height="300"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig8.png" target="_blank">Click here to open image 8.</a>
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/fig9.png" target="_blank">Click here to open image 9.</a>
</p>

<p align="center">
   <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/laplace_c3_S_R_invdist2.gif" target="_blank"><img src="figs/RBF_s2_S_R_R1.gif" width="400" height="300"></a>
</p>

<p align="center">
  <a href="https://github.com/ChairOfComputationalMathematics/poissonOptimalShapeControl/blob/master/figs/RBF_s2_S_R_R1.gif" target="_blank">Click here to open animation 3.</a>
</p>

## Author

* **Jose Lorenzo Gomez**

## Acknowledgments

This project has received funding from the European Research Council (ERC) under the European  Union’s Horizon 2020 research and innovation programme (grant agreement No. 694126-DyCon).
 
[DyCon Webpage](http://cmc.deusto.eus/dycon/)

## References

* O. Pironneau. _Optimal shape design for elliptic systems_. Springer Science & Business Media, 2012.
* J Simon. _Diferenciación de problemas de contorno respecto del dominio_. Technical report, Universidad de Sevilla, Facultad de Matemáticas, Departamento de Análisis Matemático, 1989.

Linear Elasticity mesh motion method:
* Andrew A. Johnson and Tayfun E. Tezduyar. Mesh update strategies in parallel finite element computations of flow problems with moving boundaries and interfaces. _Computer methods in applied mechanics and engineering_, 119(1-2):73–94, 1994.
* Thomas D. Economon, Francisco Palacios, and Juan J. Alonso. Unsteady continuous adjoint approach for aerodynamic design on dynamic meshes. _AIAA Journal_, 53(9):2437–2453, 2015.
* George S. Eleftheriou and Guillaume Pierrot. Rigid motion mesh morpher: A novel approach for mesh deformation. In _OPT-i, An International Conference on Engineering and Applied Sciences Optimization_, Kos, Greece, pages 4–6, 2014.

Solid Body Rotation (SBR) Stress method:
* Richard P. Dwight. Robust mesh deformation using the linear elasticity equations. In _Computational fluid dynamics 2006_, pages 401–406. Springer, 2009.

Laplacian Smoothing:
* Peter Hansbo. Generalized laplacian smoothing of unstructured grids. _International Journal for Numerical Methods in Biomedical Engineering_, 11(5):455–464, 1995.
* Rainald Löhner and Chi Yang. Improved ale mesh velocities for moving bodies. _Communications in numerical methods in engineering_, 12(10):599–608, 1996.
* Hrvoje Jasak and Zeljko Tukovic. Automatic mesh motion for the unstructured finite volume method. _Transactions of FAMENA_, 30(2):1–20, 2006.

Spring Analogy:
* Ch. Farhat, C. Degand, B. Koobus, and M. Lesoinne. Torsional springs for two-dimensional dynamic unstructured fluid meshes. _Computer methods in applied mechanics and engineering_, 163(1-4):231–245, 1998.
* Christoph Degand and Charbel Farhat. A three-dimensional torsional spring analogy method for unstructured dynamic meshes. _Computers & structures_, 80(3-4):305–316, 2002.
* Carlo L Bottasso, Davide Detomi, and Roberto Serra. The ball-vertex method: a new simple spring analogy method for unstructured dynamic meshes. _Computer Methods in Applied Mechanics and Engineering_, 194(39-41):4244–4264, 2005.

Radial Basis Functions mesh morphing:
* Stefan Jakobsson and Olivier Amoignon. Mesh deformation using radial basis functions for gradient-based aerodynamic shape optimization. _Computers & Fluids_, 36(6):1119–1136, 2007.
* AM Morris, CB Allen, and TCS Rendall. Cfd-based optimization of aerofoils using radial basis functions for domain element parameterization and mesh deformation. _International Journal for Numerical Methods in Fluids_, 58(8):827–860, 2008.
* Daniel Sieger, Stefan Menzel, and Mario Botsch. High quality mesh morphing using triharmonic radial basis functions. In _Proceedings of the 21st International Meshing Roundtable_, pages 1–15. Springer, 2013.
* Marco Evangelos Biancolini. _Fast Radial Basis Functions for Engineering Applications_. Springer, 2018.
* Fank Martijn Bos. _Numerical simulations of flapping foil and wing aerodynamics: Mesh deformation using radial basis functions_. PhD thesis, Technische Universiteit Delf, 2010.
* Armin Beckert and Holger Wendland. Multivariate interpolation for fluid-structure-interaction problems using radial basis functions. _Aerospace Science and Technology_,
5(2):125–134, 2001.
* A De Boer, MS Van der Schoot, and Hester Bijl. Mesh deformation based on radial basis function interpolation. _Computers & structures_, 85(11-14):784–795, 2007.
* Holger Wendland. _Konstruktion und Untersuchung radialer Basisfunktionen mit kompaktem Träger_. PhD thesis, Göttingen, Georg-August-Universität zu Göttingen, Diss, 1996.

Free Form Deformation technique:
* Matteo Lombardi, Nicola Parolini, Alfio Quarteroni, and Gianluigi Rozza. Numerical
simulation of sailing boats: Dynamics, fsi, and shape optimization. In _Variational Analysis and Aerospace Engineering: Mathematical Challenges for Aerospace Design_, pages 339–377. Springer, 2012.
* Thomas W Sederberg and Scott R Parry. Free-form deformation of solid geometric models. _ACM SIGGRAPH computer graphics_, 20(4):151–160, 1986.
* Michele Andreoli, Janka Ales, and Jean-Antoine Désidéri. _Free-form-deformation parameterization for multilevel 3D shape optimization in aerodynamics_. PhD thesis, INRIA, 2003.
