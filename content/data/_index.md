---
title: Forest Data
summary: "Drone-based forest mapping data, traditional field-based reference data, and guidance for new data collection"

show_date: false
profile: false
image:
  focal_point: ''
  preview_only: true
  # caption: Automatically detected treetops, with point size indicating tree height, overlaid on drone-derived orthoimagery from the Tahoe National Forest

banner:
  caption:
  image: "tree-points.png"

---


## [<i class="fa-regular fa-images"></i> **Drone-derived data**](drone/)

We host a large database of 600 drone-based forest imagery acquisitions, including raw images and downstream products such as orthomosaics, canopy height models, and individual tree detections. The data can be browsed in our [web map](/data/drone/) or accessed programmatically using HTTP or S3 ([details here](https://zenodo.org/records/23402904)).

In addition the catalog of individual drone collects linked above, we also have a collection of [composite datasets](drone-composites/), derived from oblique and nadir drone collects processed together, that are particularly well suited for tree species classification due to the multiple views of each tree from many angles.


## [<i class="fa-solid fa-tree"></i> **Ground reference data**](ground-ref/)

We host a large dataset of > 150 traditional ground-based forest inventory plots with individual tree locations mapped. These datasets generally fall within the footprint of an OFO drone-based dataset, enabling calibration and validation of drone-based forest mapping workflows.


## [<i class="fa-solid fa-clipboard-list"></i> **Data collection protocols**](/workflows/data-collection)

We provide detailed protocols for collecting the drone and field data. Check out our methods and get guidance for collecting (and, we hope, contributing!) your own drone and field-based forest data.

[<i class="fa-solid fa-plane"></i> Drone data collection protocol](/workflows/data-collection/drone/)

[<i class="fa-solid fa-clipboard-list"></i> Ground reference data collection protocol](/workflows/data-collection/ground-reference/)
