# Project Report - Computer Animation

**Taiki Yoshino**   
University of California San Diego, Computer Scinece and Engineering  
CSE169 Computer Animation (2025 Winter)  
Used Tools: C++, OpenGL, ImGUI

## Skeleton
I implemented a program that loads a character skeleton from a file and displays it in 3D. The program performs forward kinematics computations to generate world-space matrices for the joints. Additionally, I added a simple GUI using ImGui that allows the user to interactively adjust any of the skeleton's degrees of freedom (DOFs).
<div style="display: flex; justify-content: space-around;">
  <div style="width: 50%; text-align: center;">
    <img src="..\images\animation\hw1\test.gif" style="width: 100%;">
    <p>Skeleton</p>
  </div>
  <div style="width: 50%; text-align: center;">
    <img src="..\images\animation\hw1\wasp.gif" style="width: 100%;">
    <p>Wasp</p>
  </div>
    <div style="width: 50%; text-align: center;">
    <img src="..\images\animation\hw1\dragon.gif" style="width: 100%;">
    <p>Dragon</p>
  </div>
</div>

## Skin 
I developed a program that loads a character skin and attaches it to a skeleton. The skin is rendered using two different colored lights (red and blue). To accelerate rendering, I implemented skinning on the GPU by passing the entire array of the skeleton matrices to GLSL vertex shader.
<div style="display: flex; justify-content: space-around;">
  <div style="width: 35%; text-align: center;">
    <img src="..\images\animation\hw2\tube.png" style="width: 100%;">
    <p>Tube</p>
  </div>
  <div style="width: 35%; text-align: center;">
    <img src="..\images\animation\hw2\wasp.png" style="width: 100%;">
    <p>Wasp</p>
  </div>
</div>

## Keyframe Animation

## Cloth Simulation

