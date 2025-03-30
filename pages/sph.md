# Project Report - SPH

**Taiki Yoshino**   
University of California San Diego, Computer Scinece and Engineering  
CSE169 Computer Animation (2025 Winter)  
Used Tools: C++, OpenGL, ImGUI

## Particle Based Fluid Simulation
I implemented a basic Smoothed Particle Hydrodynamics simulation with 3K particles. The particles are initialized as a blob above the ground and drop under gravity, creating a splash-like effect. The system includes spring-like wall and ground repulsion, and the particles interact using SPH forces based on density and pressure. 

<div style="display: flex; justify-content: space-around;">
  <div style="width: 50%; text-align: center;">
    <img src="..\images\animation\hw5\sph.gif" style="width: 100%;">
  </div>
</div>


