---
title: Photogrammetry workflow
summary: "Drone-based forest mapping data, traditional field-based reference data, and guidance for new data collection"

date: 2022-01-01
show_date: false
profile: true
image:
  focal_point: ''
  preview_only: true
  # caption: Automatically detected treetops, with point size indicating tree height, overlaid on drone-derived orthoimagery from the Tahoe National Forest

# banner:
#   caption:
#   image: "tree-points.png"

---

**Workflow details in development**

We collect many partially overlapping drone photos across the site. This means any given tree appears in many photos, each from a slightly different angle.

{{< figure src="photogrammetry.jpg" caption="Example of an individual tree viewed from multiple angles in separate drone images." >}}

Because each tree is visible from multiple angles, it is possible to use methods related to stereo vision (specifically, *photogrammetry*) to estimate each tree's 3D structure. The photogrammetry algorithm produces a 3D cloud of points that is very similar to lidar data.

{{< figure src="lidar.PNG" caption="Visualization of a 3D point cloud from our Emerald Point site produced via photogrammetry." >}}

The photogrammetry algorithm is also used to produce an orthomosaic, which is a high-resolution aerial image produced by stitching together the numerous drone photos. It resembles NAIP or Google Earth imagery but is generally much higher resolution (~ 3 cm).

Photogrammetric processing requires parameterization for the specific application. We have tested parameterizations for individual tree detection in structurally complex conifer forests and published our results, including recommended parameter values, in [<i class="far fa-file-lines"></i> Methods in Ecology and Evolution](https://besjournals.onlinelibrary.wiley.com/doi/10.1111/2041-210X.13860). We also maintain a [<i class="fab fa-github"></i> software library](https://github.com/open-forest-observatory/automate-metashape) that makes it easy to run multiple photogrammetry workflows with pre-specified parameterizations in a documented, reproducible way.

<br>