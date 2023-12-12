---
title: "Basics"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

<!-- - How do you write a lesson using R Markdown and `{sandpaper}`?-->
- How do you cupture images and create 3d models for 3D digital preservation and publication ?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

<!-- - Explain how to use markdown with the new lesson template
- Demonstrate how to include pieces of code, figures, and nested challenge blocks-->
- Explain how the Photogrammetry capturing process works.
- Explain the techniques for creating 3d objects from 2d images positioned at a different interval in space with specialized software.

::::::::::::::::::::::::::::::::::::::::::::::::



## Definition
Photogrammetry is the art, science, and technology of 
obtaining spatial information 
about physical objects and environments 
through processes of capturing, 
measuring and interpreting photographic 2d images by mean of **triangulation**.
![https://upload.wikimedia.org/wikipedia/commons/thumb/2/2c/TriangulationIdeal.svg/1280px-TriangulationIdeal.svg.png?20070822205517](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2c/TriangulationIdeal.svg/1280px-TriangulationIdeal.svg.png?20070822205517)*Triangulation meaning in photogrammetry - from wikipedia: https://en.wikipedia.org/wiki/Triangulation_(computer_vision)*

From this process the obtained information can be used to generate [point-clouds](https://en.wikipedia.org/wiki/Point_Cloud) where each point has now three-dimensional coordinates.

![https://data.d4science.org/shub/E_aFlFV0paV3RQaGQwTkJrTGVpd0pVVktJdFpEeXh4b2gySU8yMjJTNGJybFc4Z2JNS2tqWm5raHRXK0U4VHFVRA==](https://data.d4science.org/shub/E_aFlFV0paV3RQaGQwTkJrTGVpd0pVVktJdFpEeXh4b2gySU8yMjJTNGJybFc4Z2JNS2tqWm5raHRXK0U4VHFVRA==)*Dense Point Cloud example of a small object*


These points can be further use to create a [3d meshes by mean of onother type of triangulation](https://en.wikipedia.org/wiki/Mesh_generation). 

![https://data.d4science.org/shub/E_a0hoL2Y2dmZpREorYjNGTkx3QXBGcnZoQUd5NlhIVHQ0eStLZkVMd0hXN2RhckxRMDM5dG9ralpMaFFlSEs4cg==](https://data.d4science.org/shub/E_a0hoL2Y2dmZpREorYjNGTkx3QXBGcnZoQUd5NlhIVHQ0eStLZkVMd0hXN2RhckxRMDM5dG9ralpMaFFlSEs4cg==)*3d Mesh of a small object*


The mesh can then be [texture mapped](https://en.wikipedia.org/wiki/Texture_mapping) for the final realistic appearance of the studied subject.

![https://data.d4science.org/shub/E_ZEp0UkZxbFFvdUVXN29QMmtqWldTdDlBRnBhZUdUcTBPZUhJbG44ZEFLOEsxM2R5dlBZaE1yUG9XVUZzcHZBVg==](https://data.d4science.org/shub/E_ZEp0UkZxbFFvdUVXN29QMmtqWldTdDlBRnBhZUdUcTBPZUhJbG44ZEFLOEsxM2R5dlBZaE1yUG9XVUZzcHZBVg==)*3d Mesh with texture of a small object*



<!--Underlying technology is more familiar
that we think! We can happily ignore 
the concepts and formulas used 
in the software. 

But it is useful to be aware of what it works.-->


## Photogrammetry Process

Basic steps of the photogrammetry process

1. Feature detection
2. Feature matching
3. Structure reconstruction


### Feature detection

Features are "interest points" or 
"key points" in an image. 
The goal of this step is to find 
points which are repeatable and distinctive.
Corners and other distinctive patterns 
in the image are obvious features to consider.

:::::::::::challenge 

## Try it yourself?
What points would you choose?
:::::::
:::::::::::::solution
aaa
::::::::::::::::::::

 
### Feature matching

Find correspondences of features across 
different views. 
The goal of this step is to 
detect (at least some of) 
correspondence between features in 
two or more images. 

We want a reliable result.



:::::::::::challenge 

## Try it yourself?
Do the features below correspond with each other?

:::::::
:::::::::::::solution

::::::::::::::::::::

### Structure reconstruction

Load all extracted features from an 
initial pair of images. Builds a 
projection of the points in 3D space by using the camera position.


The scene is incrementally 
extended by adding new images and 
triangulating new points. A much denser set of features is produced.

The output of this process is 
a "point cloud" or a collection of points. 
The 3D model is created by creating a
triangular mesh. The texture is then mapped to this surface.
 
 
## Lessons for acquisition

- Capture images with good texture.
- Avoid completely texture-less, 
transparent and reflective images. 
The computer will have difficulty 
finding and matching features.
- If the scene does not contain 
enough texture itself, you could 
place additional background objects, 
such as posters, etc.

