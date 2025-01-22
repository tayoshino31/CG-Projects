# Project Report - Rendering Algorithm

**Taiki Yoshino, David Choi**   
University of California San Diego, Computer Scinece and Engineering  

## Path Tracing
We implemented ray tracing and path tracing using c++ and NVIDIA's OptiX API. The GPU-based ray tracer achieved lightning-fast rendering, and the dragon was rendered in less than 2 seconds with the acceleration structure. 

<div style="display: flex; align-items: center; justify-content: space-between; gap: 20px;">
    <div>
        <table border="1" style="border-collapse: collapse; text-align: center;">
            <tr>
                <th>(Milliseconds)</th>
                <th>Without BVH</th>
                <th>With BVH</th>
            </tr>
            <tr>
                <td>C++  (CPU)</td>
                <td>50,942,720</td>
                <td>8,775,658</td>
            </tr>
            <tr>
                <td>CUDA (GPU)</td>
                <td>3,552</td>
                <td>1,998</td>
            </tr>
        </table>
    </div>
    <div>
        <img src="..\images\raytracing\scene7.png" style="width: 50%; margin-left: 20px;">
    </div>
</div>

## Direct Lighting

<div style="display: flex; justify-content: space-around;">
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw2\analytic.png" style="width: 100%;">
    <p>Analytic</p>
  </div>
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw2\direct3x3.png" style="width: 100%;">
    <p>direct3x3</p>
  </div>
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw2\direct9.png" style="width: 100%;">
    <p>direct9</p>
  </div>
    <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw2\sphere.png" style="width: 100%;">
    <p>Sphere</p>
  </div>
</div>

## Global Illumination

<div style="display: flex; justify-content: space-around;">
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw2\cornell.png"="width: 100%;">
    <p>cornellDirect</p>
  </div>
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw3\cornellSimple.png" style="width: 100%;">
    <p>cornellSimple</p>
  </div>
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw3\cornellNEE.png" style="width: 100%;">
    <p>cornellNEE</p>
  </div>
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw3\cornellRR.png" style="width: 100%;">
    <p>cornellRR</p>
  </div>
</div>

<div style="display: flex; justify-content: space-around;">
  <div style="width: 30%; text-align: center;">
      <img src="..\images\rendering\hw2\dragon.png"="width: 100%;">
      <p>dragonDirect</p>
    </div>
  <div style="width: 30%; text-align: center;">
    <img src="..\images\rendering\hw3\dragon.png" style="width: 100%;">
    <p>dragonGI</p>
  </div>
</div>

## Multiple Important Sampling

<div style="display: flex; justify-content: space-around;">
  <div style="width: 30%; text-align: center;">
    <img src="..\images\rendering\hw4\cornellCosine.png" style="width: 100%;">
    <p>cornellCosin</p>
  </div>
  <div style="width: 30%; text-align: center;">
    <img src="..\images\rendering\hw4\cornellBRDF.png"="width: 100%;">
    <p>cornellBRDF</p>
  </div>
</div>

## Reference
1. https://developer.nvidia.com/discover/ray-tracing
2. https://en.wikipedia.org/wiki/Bounding_volume_hierarchy
3. https://tavianator.com/2014/ellipsoid_bounding_boxes.html  