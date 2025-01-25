# Project Report - Rendering Algorithm

**Taiki Yoshino, David Choi**   
University of California San Diego, Computer Scinece and Engineering  

## Ray Tracing with NVIDIA Optix
We implemented ray tracing using c++ and NVIDIA's OptiX. The GPU-based ray tracer achieved lightning-fast rendering, and the dragon was rendered in less than 2 seconds with a BVH acceleration structure. 

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
We implemented direct light sampling for area light sources using both analytic and Monte Carlo solutions. The analytic solution computes the incident radiance from a polygonal light source by projecting it onto the unit hemisphere and then onto the unit disk. Although the solution is efficient to compute and noise-free, it only works for scenes without shadows. On the other hand, the Monte Carlo solution is computationally expensive and includes noise, but it can handle arbitrary BRDFs and use shadow rays to determine if the light source is occluded.

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

## Indirect Path Tracing
To account for indirect lighting, where a surface is illuminated by light bounced off other surfaces, we implemented Monte Carlo path tracing. Since path tracing requires higher computational cost, we improved efficiency using Next Event Estimation (NEE) and Russian Roulette (RR). NEE improves convergence by directly sampling light sources at each bounce, reducing variance and speeding up rendering by capturing important lighting interactions more efficiently. RR optimizes performance by probabilistically terminating low-contribution paths, reducing computations while maintaining an unbiased estimate of the rendering equation.

<div style="display: flex; justify-content: space-around;">
  <div style="width: 45%; text-align: center;">
    <img src="..\images\rendering\hw2\cornell.png" style="width: 100%;">
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
      <img src="..\images\rendering\hw2\dragon.png" style="width: 100%;">
      <p>dragonDirect</p>
    </div>
  <div style="width: 30%; text-align: center;">
    <img src="..\images\rendering\hw3\dragon.png" style="width: 100%;">
    <p>dragonGI</p>
  </div>
</div>

## Importance Sampling
We introduced importance sampling methods into our renderer to compute indirect lighting more efficiently. The previous method, Uniform Hemisphere Sampling, distributed samples uniformly, often allocating them to less important directions, leading to slower convergence and increased noise. To improve this, we implemented PDF-based sampling techniques, specifically Cosine-Weighted Sampling and BRDF Importance Sampling. These methods prioritize sampling directions that contribute more significantly to the final radiance, improving rendering quality and efficiency.

<div style="display: flex; justify-content: space-around;">
  <div style="width: 30%; text-align: center;">
    <img src="..\images\rendering\hw4\cornellCosine.png" style="width: 100%;">
    <p>cornellCosin</p>
  </div>
  <div style="width: 30%; text-align: center;">
    <img src="..\images\rendering\hw4\cornellBRDF.png" style="width: 100%;">
    <p>cornellBRDF</p>
  </div>
</div>

