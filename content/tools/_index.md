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

Tools and workflows for processing drone imagery to map forests at the individual tree level. For walkthroughs demonstrating the use of these tools for common forest mapping tasks, see our [<i class="far fa-file-lines"></i> data workflows](../workflows/). Our tools are open-source and developed in the open on [<i class="fab fa-github"></i> GitHub](https://github.com/open-forest-observatory/).

- **[Automate Metashape](https://github.com/open-forest-observatory/automate-metashape)** - Simple command-line tool for processing drone imagery into orthomosaics, digital surface and terrain models, 3D mesh models, and point clouds in a reproducible, documented way, with default settings that work well for forests. This tool streamlines the use of the commonly used commercial photogrammetry software *Agisoft Metashape*. We are working to develop similar functionality for open-source photogrammetry software.

- **[Geograypher](https://github.com/open-forest-observatory/geograypher)** - Python and command-line toolkit for projecting geospatial data (e.g., tree species labels) onto raw drone images, and vice versa. This tool enables powerful workflows for training and deploying computer vision models for tree species identification and other tasks, taking advantage of the fact that each tree generally appears in numerous drone images from different angles.

- **[ofo R package](https://github.com/open-forest-observatory/ofo-r) (in development)** - This in-development package provides functions for common drone data operations, in many cases leaning on existing tools while providing forest-specific default settings. Supported tasks include:
  - Creating canopy height models (CHMs)
  - Detecting individual trees from CHMs and delineating tree crowns
  - Evaluating drone-based tree detections by comparing them against field reference data
  - Compiling metadata and building visualizations of new drone data acquisitions
  - Accessing datasets from the OFO drone data and field reference data catalogs

- **Geospatial data registration toolkit (in development)** - This set of tools will enable alignment of datasets with minor misalignment due to normal spatial error (e.g., orthomosaics from different dates, or a drone-derived CHM and a third-party DTM).

<br>