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

<a style="font-size: 1.3em;">
  <i class="fa-solid fa-images"></i> <strong>Drone Imagery Processing</strong>
</a>

<br/>

<a href="https://github.com/open-forest-observatory/automate-metashape" style="font-size: 1.0em;">
  <strong>Automate Metashape</strong>
</a>

 Simple command-line tool for processing drone imagery into orthomosaics, digital surface and terrain models, 3D mesh models, and point clouds in a reproducible, documented way, with default settings that work well for forests. This tool streamlines the use of the commonly used commercial photogrammetry software *Agisoft Metashape*. We are working to develop similar functionality for open-source photogrammetry software.


<a href="https://github.com/open-forest-observatory/geospatial-data-registration-toolkit" style="font-size: 1.0em;">
  <strong>Geospatial data registration toolkit</strong>
</a>

This set of tools will enable alignment of datasets with minor misalignment due to normal spatial error (e.g., orthomosaics from different dates, or a drone-derived CHM and a third-party DTM).


<br/>

<a style="font-size: 1.3em;">
  <i class="fa-solid fa-robot"></i> <strong>Machine Learning</strong>
</a>

<br/>

<a href="https://github.com/open-forest-observatory/geograypher" style="font-size: 1.0em;">
  <strong>GeogRaypher</strong>
</a>

Python and command-line toolkit for projecting geospatial data (e.g., tree species labels) onto raw drone images, and vice versa. This tool enables powerful workflows for training and deploying computer vision models for tree species identification and other tasks, taking advantage of the fact that each tree generally appears in numerous drone images from different angles.


<a href="https://github.com/open-forest-observatory/tree-detection-framework" style="font-size: 1.0em;">
  <strong>Tree Detection Framework</strong>
</a>

A python library that provides a standardized interface for performing training, inference, and evaluation using existing tree detection models and algorithms. The project currently supports the external computer vision models DeepForest, Dectree2, and SAM2, as well as a geometric canopy height model segmentor implemented within TDF. 


<a href="https://github.com/open-forest-observatory/tree-species-prediction" style="font-size: 1.0em;">
  <strong>Tree Species Prediction</strong>
</a>

A python library for predicting tree species 

<br/>


<a style="font-size: 1.3em;">
  <i class="fa-solid fa-cloud"></i> <strong>Computing Infrastructure</strong>
</a>

<br/>

<a href="https://github.com/open-forest-observatory/cacao-terraform-ofo" style="font-size: 1.0em;">
  <strong>Virtual Machine Templates</strong>
</a>

Need larger computing resources to process and analyze your drone imagery? We have developed an 'infrastructure-as-code' template that launches and provisions virtual machines loaded with aerial imagery processing tools. It is currently configured to work on the [Jetstream2 Cloud Computer](https://jetstream-cloud.org/).