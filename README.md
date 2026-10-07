# 3D_DBSCSAN
Spatio-tenporal algorithm based on 2D DBSCAN.

The algorithm uses the 2D DBSCAN package to cluster data points from NetCDF files at a daily scale. This first step uses min_samples and epsilon as the standard DBSCAN parameters. The second step of the 3D clustering process introduces three new parameters: overlap_threshold, size_ratio and centroid_offset. In the second stage, the algorithm goes through every 2d cluster, and determines whether any cluster on the next consecutive day satisifies all three of the stage 2 conditions. If that is the case, the process is repeated for the next day, until conditions are not met anymore. 

The final product is a NetCDF containing a register of all spatio-temporal clusters, with information such as daily size, centroid coordinates, etc.
