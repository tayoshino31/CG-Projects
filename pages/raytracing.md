# Project Report - Ray Tracing

**Taiki Yoshino, David Choi**   
University of California San Diego, Computer Scinece and Engineering  

## Ray Tracing
We implemented ray tracing algorithm (Whitted 1980) from scratch in C++. Thoese rendering includes the transformation of spheres and triangles, a single point light source, a maximum of five reflections, and material properties.

Additionally, we implemented a Bounding Volume Hierarchy to speed up the rendering process. This acceleration structure halved the rendering time for scene 2 from 20 minutes to 10 minutes, and significantly reduced the rendering time for scene 4 (+50K vertices) from roughly 14 hours to just 2.5 hour. For those implementing bounding volume heirarchy in the future its worth noting that if only 1/4 of your image is rendering properly chances are you just need to check maxT and minT for you bounding volume intersection.

## Rendered Images

<div style="display: flex; justify-content: space-around;">
  <div style="width: 45%; text-align: center;">
    <img src="..\images\raytracing\scene4-specular.png" style="width: 100%;">
    <p>Scene 1</p>
  </div>
  <div style="width: 45%; text-align: center;">
    <img src="..\images\raytracing\scene5.png" style="width: 100%;">
    <p>Scene 2</p>
  </div>
</div>

<div style="display: flex; justify-content: space-around;">
  <div style="width: 45%; text-align: center;">
    <img src="..\images\raytracing\scene6.png" style="width: 100%;">
    <p>Scene 3</p>
  </div>
  <div style="width: 45%; text-align: center;">
    <img src="..\images\raytracing\scene7.png" style="width: 100%;">
    <p>Scene 4</p>
  </div>
</div>

## Ray Tracing Method

**Ray Tracing Overview [(NVIDIA'19)](https://developer.nvidia.com/discover/ray-tracing):**

<div class="flex-container" style="display: flex;">
  <img src="..\images\
raytracing\ray-tracing.jpeg" style="width: 50%;">
  <ol>
    <li>Cast a ray into every pixel.</li>
    <li>Determine if it intersects any object, and find the nearest one.</li>
    <li>Find the color of intesected point based on the materials and light position.</li>
    <li>Recursively generate a new ray to the reflection direction.</li>
    <li>Determine the final color of the pixel.</li>
  </ol>
</div>
  
  
**Code Snippet:**





[//]: # ({% raw %})
```C++
RayTrace(Camera cam, Scene scene, int width, int height)
{
    Image image = new Image (width, height);
    for(int h = 0; h < height; h++){
        for(int w = 0; w < width; w++){
            Ray ray = RayThruPixel (cam, h, w);
            Intersection hit = Intersect (ray, scene);
            image[h][w] = FindColor (hit);
        }
    }
    return image;
}
```
[//]: # ({% endraw %})


## Acceleration Structure
**Bounding Volume Hierarchy: [(BVH)](https://en.wikipedia.org/wiki/Bounding_volume_hierarchy)**
  
  <img src="..\images/raytracing/BVH.png" style="width: 70%;">

Testing every primitive for ray intersection is extremely slow as the number of objects increases. An acceleration structure efficiently selects only some potential primitives for intersection with the ray. BVH first builds a hierarchy of bounding volumes as a binary tree and uses it to accelerate ray intersection. BVH allows the ray to find the intersection in at most O(log(n)).

## Reference
1. https://developer.nvidia.com/discover/ray-tracing
2. https://en.wikipedia.org/wiki/Bounding_volume_hierarchy
3. https://tavianator.com/2014/ellipsoid_bounding_boxes.html  
