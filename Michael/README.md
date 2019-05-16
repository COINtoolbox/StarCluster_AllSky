# Strategy
My region flagging algorithm is designed to identify candidate groups of young stellar objects. It is possible that some of these groups might be missed by methods optimized for detection of older clusters because these clusters typically lie along complex lines of sight that can be affected by spatially variable extinction and nebulosity. If this method succeeds in identifying clusters missed by other methods, it might be useful to use as a supplemental method for the Galactic plane. 

The method has three steps:
1. Candiate young stellar objects are identified from infrared photometric data. I used the 2MASS and GLIMPSE 360 survey data, which provides photometry in the J, H, Ks, 3.6 micron, and 4.5 micron bands. These data are available for approximately 1 degree above and below the Galactic plane. Stars with red colors are identified using the color selection criteria from Gutermuth et al. (2008). However, this identifies not only young stellar objects, but many contaminants, including many reddened field stars located behind clouds. As a result, the contaminants are not necessarily uniformly distributed, but may be spatially clustered following the outline of molecular clouds. 
2. From this subset I use a modified version of the UPMASK algorithm to identify spatially clustered groups with common proper motions. The main modification to the UPMASK is that I use the two-point correlation function to test whether a subset of stars with similar proper motions are more strongly spatially clustered than the whole set of stars. This means that we don't necessarily need to assume that the non-members are uniformly distributed.
3. From the resulting catalog of candidate young stellar objects, I identify possible clusters using HDBSCAN.

# Results
