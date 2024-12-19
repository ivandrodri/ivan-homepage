---
layout: default
title: CNC milling simulation. 
permalink: /projects/
---

{% include lib/mathjax.html %}

## Innovative GPU-Based Milling/Collision Simulator

### The Challenge  
The milling process involves a **sequential dependency**:  

At each time step $$t = j$$, the material shape depends on all previous steps ( $$t = 0$$  to  $$t = j-1$$ ) .
To compute collisions: 

- The simulation runs **sequentially**, leading to a complexity of $$ O(N) $$, where $$ N \sim 10^6 $$ for complex shapes.

**Even with parallel collision detection at a single time step, the sequential nature remains a bottleneck**.

### Existing Solutions  

CAM software typically computes collisions in **time windows**:

- ✅ Speeds up simulations.  
- ⚠️ Risks **false positives** for collisions.  
- ⚠️ Produces **suboptimal tool paths**, relying on CAM programmer experience to avoid potential issues.

---

### Our Solution

We developed an **innovative, fully parallelizable approach** using a **reduction operation/error-correction method**:  

- Transforms the sequential \( O(N) \) problem into a **fully parallel** one with complexity \( O(\log N) \).  
- Implemented entirely on the **GPU** for maximum performance.
- EU/USA patents granted

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WebM Video</title>
</head>
<body>
    <h1>My WebM Video</h1>
    <video width="640" height="360" controls>
        <source src="../assets/videos/cnc_simul.webm" type="video/webm">
        Your browser does not support the video tag.
    </video>
</body>
</html>

---

### Key Features  
- 🚀 **Fully GPU-Accelerated**: The milling/collision simulator runs completely inside the GPU.
- 🧩 **Two-Voxelization Model**:  
   - Saves **local milling and collision data** for the work-piece.  
   - Optimizes calculations to achieve parallel processing efficiency.
   - For the two voxelization model we implemented the method developed in the paper 
     [Fast parallel surface and solid voxelization on GPUs](https://dl.acm.org/doi/abs/10.1145/1882261.1866201) . 
     For a simple version of the voxelizer give a look to my [repo]()
    
    ToDo: --> Add an image here  

-  Another cool aspect of this project is the use of template metaprogramming!
    
    ToDo: --> Show metatemplate code
 
---

This method significantly reduces simulation time while ensuring **accurate, collision-free tool paths**. 

BONUS: 

Leverage this high-speed simulator to **optimize toolpaths** further using advanced techniques, such as 
**Reinforcement Learning**, to enhance performance and accuracy even more.


<a href="/ivan-homepage/">
    <button style="padding:10px 20px; background-color:#007BFF; color:white; border:none; border-radius:5px; cursor:pointer;">
        Back to Home
    </button>
</a>