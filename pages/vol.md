# Project Report - Volumetric Path Tracer

**Taiki Yoshino**   
University of California San Diego, Computer Scinece and Engineering  
CSE272 Advanced Image Synthesis (2025 Winter)  
Used Tools: C++, lajolla renderer

## Homogeneous Media
I implemented a volumetric path tracer for multiple monochromatic homogeneous media with absorption and multiple scattering. The algorithm includes phase function sampling, next event estimation, and surface lighting via BSDF evaluation.

<div style="display: flex; justify-content: space-around;">
  <div style="width: 33%; text-align: center;">
    <img src="..\images\volume\volpath_test6.png" style="width: 100%;">
    <p>Spheres</p>
  </div>
  <div style="width: 33%; text-align: center;">
    <img src="..\images\volume\vol_cbox.png" style="width: 100%;">
    <p>Cornell Box</p>
  </div>
  <div style="width: 33%; text-align: center;">
    <img src="..\images\volume\vol_cbox_teapot.png" style="width: 100%;">
    <p>Cornell Box Teapod</p>
  </div>
</div>


## Heterogeneous Media
I extended the volumetric path tracer to support chromatic heterogeneous volumes using null-scattering. This allows rendering of volumes with spatially and spectrally varying densities.

<div style="display: flex; justify-content: space-around;">
  <div style="width: 35%; text-align: center;">
    <img src="..\images\volume\hetvol.png" style="width: 100%;">
    <p>Heterogeneous</p>
  </div>
  <div style="width: 35%; text-align: center;">
    <img src="..\images\volume\hetvol_colored.png" style="width: 100%;">
    <p>Heterogeneous Colored</p>
  </div>
</div>

