# Project Report - Cloth Simulation

**Taiki Yoshino**   
University of California San Diego, Computer Scinece and Engineering  
CSE169 Computer Animation (2025 Winter)  
Used Tools: C++, OpenGL, ImGUI

## Cloth
I implemented cloth simulation using particles. The cloth responds to uniform gravity, spring elasticity, damping, aerodynamic drag, and collisions with a ground plane. The top-row particles are fixed to hold the cloth up, and I added interactive controls that allow the user to move these fixed points. 

<div style="display: flex; justify-content: space-around;">
  <div style="width: 50%; text-align: center;">
    <img src="..\images\animation\hw4\cloth.gif" style="width: 100%;">
  </div>
</div>


## Parachute
I implemented a parachute simulation by extending the cloth system to support ropes and rigid bodies. A cubic is attached to a cloth with spring-damper ropes.

<div style="display: flex; justify-content: space-around;">
  <div style="width: 50%; text-align: center;">
    <img src="..\images\animation\hw4\parachute.gif" style="width: 100%;">
  </div>
</div>
