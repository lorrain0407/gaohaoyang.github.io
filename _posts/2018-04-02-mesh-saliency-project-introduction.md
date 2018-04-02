---
layout: post
title:  "Mesh Saliency"
date:   2018-04-02 22:10:16
categories: research
tags: research graphics matlab
---

* content
{:toc}

Achieve this paper: [Lee C H, Varshney A, Jacobs D W. Mesh saliency[C]//ACM transactions on graphics (TOG). ACM, 2005, 24(3): 659-666.](https://www.cs.umd.edu/gvil/papers/mesh_saliency_sig05.pdf)

## User Guidance: 

The main files are in Mesh-Saliency/worksheet, including modles(.ply) and executable files(.m). Others also should be added into matlab's path.

Firstly, when you want to see the saliency of the model, run prepareDataWS.m for preparing some essential data.

Secondly, run pipelineDemo.m

[saliency, az, el, az2, el2] = meshSaliencyPipeline(Mesh)

`saliency` is the saliency value corresponding to each vertex in the input mesh.

`az`, `el` are the spherical coordinates for the most salient viewpoint.

`az2`, `el2` are the spherical coordinates for the least salient viewpoint.

Thirdly, run displayResults.m and then you can see the mesh saliency in special spherical coordinates.

Step 1-3 refered to [this page](http://research.dshin.org/code/saliency-for-3d-meshes.html)

Finally, run maxSaliencyArea.m, you can the most saliency area can be caculated and shown in yellow.

## Realization: 

I think details in this paper is enough clear for you to realize it. Just following it! 

If there is something you do not understand, feel free to email me at lorrain0407@gmail.com.

