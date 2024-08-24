---
title: Tree detection & mapping workflow
summary: "Detecting and mapping individual trees using photogrammetry products"

show_date: false
profile: false
image:
  focal_point: ''
  preview_only: true
  # caption: Automatically detected treetops, with point size indicating tree height, overlaid on drone-derived orthoimagery from the Tahoe National Forest

# banner:
#   caption:
#   image: "tree-points.png"

---

**Workflow details in development**

### Canopy height model (CHM) production

After creation of a point cloud via photogrammetry, we process it to compute a digital surface model (DSM). The DSM is a high-resolution (~10-cm) raster indicating the elevation of the vegetation (or ground) surface in each pixel. Then, we subtract elevation values from a high-resolution digital elevation model (DEM). The result is a canopy height model (CHM) indicating the height of the vegetation above the ground in each pixel.

{{< gallery album="photogrammetry" >}}


### Tree detection

Next, using an algorithm such as (a) the variable-window filter implemented in the [ForestTools](https://cran.r-project.org/web/packages/ForestTools/) R package or (b) [DeepForest](https://github.com/weecology/DeepForest) with some post-processing, we detect individual tree tops, and their associated heights, from the canopy height model. The selection and parameterization of the optimal tree detection algorithm is a complex process and can depend on the approach used for drone imagery collection and processing. We have evaluated the interactions between these choices and identified a an accurate tree detection method and parameterization for structurally complex conifer forests. The results are published in [<i class="far fa-file-lines"></i> Methods in Ecology and Evolution](https://besjournals.onlinelibrary.wiley.com/doi/10.1111/2041-210X.13860).