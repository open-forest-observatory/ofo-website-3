---
title: Automated Forest Mapping Tools
summary: "Tools to map forests at the individual tree level using drones, photogrammetry, and computer vision"

image:
  focal_point: ''
  preview_only: true
  # caption: Automatically detected treetops, with point size indicating tree height, overlaid on drone-derived orthoimagery from the Tahoe National Forest

banner:
  caption:
  image: "tree-points.png"

---

Tools for processing drone and ground imagery to map forests at the individual tree level. Our tools are open-source and developed in the open on [<i class="fab fa-github"></i> GitHub](https://github.com/open-forest-observatory/).

{{% callout note %}}
Check out our [tutorials](https://docs.openforestobservatory.org/tutorials/) to learn how to use these tools in real data processing workflows.
{{% /callout %}}


## <i class="fa-solid fa-tree"></i> **Tree detection and classification**

[**Tree Detection Framework**](https://github.com/open-forest-observatory/tree-detection-framework)\
A Python library for detecting and delineating individual trees from drone-derived data products. It provides a geometric algorithm that finds treetops in a canopy height model and a common interface to several existing computer vision models that detect trees in an orthomosaic. It eliminates the need for common 'boilerplate' pre- and post-processing code, including dividing large geospatial rasters into the smaller tiles expected by computer vision models and reassbmeling the results. It facilitates comparing among different computer vision models, using consistent inputs and outputs.

[**Tree Classification Framework**](https://github.com/open-forest-observatory/tree-classification-framework) \
A Python library for predicting tree attributes, such as species and live/dead status, from raw drone photos. In the tutorials it crops each view of each detected tree out of the drone photos, preparing the crops for a computer vision classification model, and afterward aggregates the predictions for all crops of a tree into a single prediction for that tree.

[**Tree Registration and Matching Toolkit (TRAM)**](https://github.com/open-forest-observatory/tree-registration-and-matching)\
A Python library for spatially aligning and comparing different tree maps. It can estimate the spatial offset between a ground reference (manual inventory) tree map and drone-derived data, such as a canopy height model or set of detected trees. It also matches the corresponding trees between two datasets (e.g., ground survey and drone detections), allowing a spatial tolerance. Finally, it supports computing metrics of agreement (detection accuracy), such as recall and precision, between two tree maps.

[**Geograypher**](https://github.com/open-forest-observatory/geograypher)\
Python and command-line toolkit for projecting geospatial data (e.g., tree species labels) onto raw drone images, and vice versa. This tool enables powerful workflows for training and deploying computer vision models for tree species identification and other tasks, taking advantage of the fact that each tree generally appears in numerous drone images from different angles.

## <i class="fa-solid fa-images"></i> **Drone imagery processing & alignment**

[**Automate Metashape**](https://github.com/open-forest-observatory/automate-metashape)\
Simple command-line tool for processing drone imagery into orthomosaics, digital surface and terrain models, 3D mesh models, and point clouds in a reproducible, documented way, with default settings that work well for forests. This tool streamlines the use of the commonly used commercial photogrammetry software *Agisoft Metashape*. We are working to develop similar functionality for open-source photogrammetry software.

[**Geospatial Data Registration Toolkit**](https://github.com/open-forest-observatory/geospatial-data-registration-toolkit)\
This set of tools enables alignment of raster datasets with minor misalignment due to normal spatial error (e.g., orthomosaics from different dates, or a drone-derived CHM and a third-party DTM).

<br/>
