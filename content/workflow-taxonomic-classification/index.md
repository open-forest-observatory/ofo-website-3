---
title: Tree taxonomic classification workflow
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

After identifying the locations and sizes of individual trees, the next step is to identify each tree taxonomically. The [Geograypher](https://github.com/open-forest-observatory/geograypher) tool enables powerful workflows for training and deploying computer vision models for tree taxonomic identification and other tasks, taking advantage of the fact that each tree generally appears in numerous drone images from different angles. The tool enables projection of geospatial data (e.g., tree species labels) onto raw drone images, and vice versa, taking advantage of the fact that if we know the precise position of the drone camera and the parameters of its lens, we can translate any given pixel in a drone image into a ray through 3D geospatial space.

{{< figure src="multiview-species-id.png" width="500px" title="Workflow for programmatically isolating images of individual detected trees for AI-based species identification. (1) The tree is detected using the CHM, orthomosaic, and/or point cloud. (2) Points defining the boundary of the tree in 3D geospatial space are projected onto a raw drone image. (3) The raw image of the focal tree can be cropped and/or labeled. (4) The process is repeated for every drone image in which the focal tree appears. The resulting images are supplied to the computer vision image classification algorithm." >}}

Using Geograypher, a geospatial map (e.g. of species identities) can be projected onto the raw drone images and used (for example) for training a computer vision algorithm to identify tree species (or detect trees) using the raw drone images. Similarly, if one has tree species identities annotated on the raw drone images (e.g., the result of running computer vision inference on the images), the MVMT can project these annotations onto the geospatial layers (e.g. orthomosaic) for mapping purposes.

<br>