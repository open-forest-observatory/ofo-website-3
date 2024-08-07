---
title: Drone-based forest mapping tools
summary: "Tools to map forests at the individual tree level using drones, photogrammetry, and computer vision"

date: 2022-01-01
show_date: false
profile: true
image:
  focal_point: ''
  preview_only: true
  # caption: Automatically detected treetops, with point size indicating tree height, overlaid on drone-derived orthoimagery from the Tahoe National Forest

banner:
  caption:
  image: "tree-points.png"

gallery_item:
- album: photogrammetry
  image: 1-dsm.png
  caption: Digital surface model
- album: photogrammetry
  image: 2-chm.png
  caption: Canopy height model
- album: photogrammetry
  image: 3-orthomosaic.png
  caption: Orthomosaic
- album: photogrammetry
  image: 4-stem-map.png
  caption: Treetops, with point size proportional to tree height, overlaid on orthomosaic

---

Tools and workflows for processing drone imagery to map forests at the individual tree level.

- **[Automate Metashape](https://github.com/open-forest-observatory/automate-metashape)** - Tool for processing drone imagery into orthomosaics, digital surface and terrain models, 3D mesh models, and point clouds in a reproducible, documented way, with default settings that work well for forests. This tool streamlines the use of the commonly used commercial photogrammetry software *Agisoft Metashape*. We are working to develop similar functionality for open-source photogrammetry software.

- **[Geograypher](https://github.com/open-forest-observatory/geograypher)** - Toolkit for projecting geospatial data (e.g., tree species labels) onto raw drone images, and vice versa. This tool enables powerful workflows for training and deploying computer vision models for tree species identification and other tasks, taking advantage of the fact that each tree generally appears in numerous drone images from different angles.

- **[ofo R package](https://github.com/open-forest-observatory/ofo-r) (in development)** - This in-development package provides functions for common drone data operations, in many cases leaning on existing tools while providing forest-specific default settings. Supported tasks include:
  - Creating canopy height models (CHMs)
  - Detecting individual trees from CHMs and delineating tree crowns
  - Evaluating drone-based tree detections by comparing them against field reference data
  - Compiling metadata and building visualizations of new drone data acquisitions
  - Accessing datasets from the OFO drone data and field reference data catalogs

- **Geospatial data registration toolkit (in development)** - This set of tools will enable alignment of datasets with minor misalignment due to normal spatial error (e.g., orthomosaics from different dates, or a drone-derived CHM and a third-party DTM).


### Data processing workflows

Different OFO tools come in at different points within various drone data processing workflows. We provide step-by-step guides for some common data processing tasks.

- [Image collection](/workflow-data-collection/) - collecting drone data to support forest mapping at the individual-tree scale
- [Photogrammetry](/workflow-photogrammetry/) - processing drone data into geospatial datasets including orthomosaics, digital surface and terrain models, 3D mesh models, and point clouds
- [Tree detection & mapping](/workflow-tree-detection/) - detecting and mapping individual trees using photogrammetry products
- [Taxonomic identification](/workflow-taxonomic-classification/) - taxonomically classifying trees from drone imagery in a geospatial context

<br>