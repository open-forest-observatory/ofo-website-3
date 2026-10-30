---
title: Drone-based forest mapping tools
summary: "Tools to map forests at the individual tree level using drones, photogrammetry, and computer vision"

image:
  focal_point: ''
  preview_only: true
  # caption: Automatically detected treetops, with point size indicating tree height, overlaid on drone-derived orthoimagery from the Tahoe National Forest

banner:
  caption:
  image: "tree-points.png"

---

Tools and workflows for processing and analyzing drone imagery to map forests at the individual tree level. Our tools are open-source and developed in the open on [<i class="fab fa-github"></i> GitHub](https://github.com/open-forest-observatory/).

<br/>

## <i class="fa-solid fa-images"></i> **Drone imagery processing**


[**Automate Metashape**](https://github.com/open-forest-observatory/automate-metashape)\
Simple command-line tool for processing drone imagery into orthomosaics, digital surface and terrain models, 3D mesh models, and point clouds in a reproducible, documented way, with default settings that work well for forests. This tool streamlines the use of the commonly used commercial photogrammetry software *Agisoft Metashape*. We are working to develop similar functionality for open-source photogrammetry software.

[**Geospatial Data Registration Toolkit**](https://github.com/open-forest-observatory/geospatial-data-registration-toolkit)\
This set of tools enables alignment of raster datasets with minor misalignment due to normal spatial error (e.g., orthomosaics from different dates, or a drone-derived CHM and a third-party DTM).

<br/>

## <i class="fa-solid fa-robot"></i> **Machine learning**

[**Geograypher**](https://github.com/open-forest-observatory/geograypher)\
Python and command-line toolkit for projecting geospatial data (e.g., tree species labels) onto raw drone images, and vice versa. This tool enables powerful workflows for training and deploying computer vision models for tree species identification and other tasks, taking advantage of the fact that each tree generally appears in numerous drone images from different angles.

[**Tree detection framework**](https://github.com/open-forest-observatory/tree-detection-framework)\
A python library that provides a standardized interface for performing training, inference, and evaluation using existing tree detection models and algorithms. The project currently supports the external computer vision models DeepForest, Dectree2, and SAM2, as well as a geometric canopy height model segmentor implemented within TDF.
