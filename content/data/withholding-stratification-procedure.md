---
title: "Data use restriction: datasets withheld from ML model training"

draft: false
show_date: false
profile: true
image:
  focal_point: ''
  preview_only: true
  # caption: Automatically detected treetops, with point size indicating tree height, overlaid on drone-derived orthoimagery from the Tahoe National Forest

banner:
  caption:
  image: "tree-points.png"

---

A random stratified subset of approximately 20% of ground plots and drone missions is to be excluded from training ML models that are intended for use by the forest mapping/ML community. For such applications, these plots are reserved for use only as test data for model evaluation and intercomparison. The ground plots and drone missions to be excluded from training are indicated by the value `true` for the metadata attribute `withheld_from_training`.

## Withheld data selection procedure

Using the contents of the OFO drone and ground reference data catalogs as of November 2025, we selected a random stratified set of ground plots and drone missions for withholding, under a set of constraints described below. Our aim was to select approximately 15-22% of the datasets (measured by the number of drone missions, ground plots, and trees in the ground plots), such that the withheld set was representative of the full catalog across a range of abiotic and biotic conditions. Selection was constrained by the spatial structure of the data; specifically, ground plots and drone missions that overlapped spatially were kept together as either all withheld or all not withheld.

For each ground plot, we computed forest structure metrics (tree density, basal area per hectare, and mean tree basal area) and species composition metrics (relative abundance by species) based on live trees with (estimated or measured) DBH > 20 cm (to standardize across plots with different minimum tree size inclusion criteria) (exception: for a set of plantation plots dominated nearly exclsively by small trees, all trees regardless of size were included). We clustered plots into 8 species composition categories using k-means clustering applied to relative species abundance of the common species (those with more than 20 individuals recorded across the entire catalog). We also extracted annual precipitation and EPA Level III ecoregion at each plot’s centroid.

We also classified plots into three tiers classes on the presence of co-located drone data containing the ground plot: (1) both high-nadir and low-oblique paired drone missions that could be spatially co-registered to the ground plot, (2) both a high-nadir and low-oblique drone mission that could not be spatially co-registered to the ground plot, (3) any drone mission, or (4) no drone mission.

We then used a forward greedy search to select ground plots to include in the withheld set. The aim was to select plots such that the histograms of biotic and abiotic conditions for the withheld dataset most closely matched their counterparts for the full dataset. The histograms used represented the three forest structure attributes, the species composition groups, abiotic attributes (precipitation, ecoregion, data collection project, and drone mission pairing class), and several interactions of the above. We proportionally scaled the magnitudes of the frequency values in the full-catalog histograms so that they summed to the same values as the withheld-set histograms. The degree of matching between the withheld set and full catalog was quantified as the mean absolute difference in plot counts across all bins, averaged over all stratification variables, with factorial combinations given 50% weight. The algorithm stopped with the withheld set reached the target percentage of 18.5% or when no further additions were possible without exceeding the 22% upper bound for plots or trees or plot groups.

The greedy search was performed first for all plots that had drone coverage. It was then performed for all plots that did not have drone coverage, initiating the selection with any plots selected by the first search that also had no drone coverage (and were initially selected only due to membership in a spatially overlapping group including plot(s) with overlapping drone missions). Finally, it was performed a third time for drone missions that did not overlap any ground plots, again adding them to the existing selected set. For this final iteration, structure and species composition metrics were not used because they were not available for drone missions with no associated ground plot data, and only abiotic stratification variables were used. Whenever adding a ground plot or drone mission (or evaluating adding it), we required the algorithm to add all plots or drone missions that were part of the same set of spatially overlapping footprints, potentially adding numerous plots or missions to the stratification histograms at once.

Two contributed ground plot projects contained a large number of small plots (NEON 2023 and Eshom 2020). These plot datasets were thinned to every 4th plot (so that ¾ of the plots were ineligible for selection into the withheld set) to prevent highly spatially clustered, numerous small plots from dominating the reference distribution or consuming too much of the withholding budget. We also excluded from withholding two large outlier datasets that each consisted of a single group (plots 0081 and 0242-0269) because they had potential to greatly skew the selected plot distributions but had no other comparable plots of other groups in the catalog. Similarly, drone mission 000078 (which encompasses ground plots 0242-0269) is explicitly excluded from withholding because there are no other comparable missions in the catalog and it encompasses many small ground plots.
