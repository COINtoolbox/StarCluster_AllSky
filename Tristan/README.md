Results were obtained by splitting the region of interest into four levels of square tiles: 1 degree edge, 0.5, 0.2, and 0.1.
In the 1 degree tiles I discarded stars with parallaxes smaller than 0.6 mas and magnitude G fainter than 15.5.
In the 0.5 degree tiles I discarded stars with parallaxes smaller than 0.3 and G fainter than 16.5.
In the 0.2 and 0.1 tiles I discarded the stars fainter than G=18.

In each tile I use a GMM to fit the proper motion space. The number of components is the total number of stars divided by 20.
A group is flagged as a potential cluster if both terms in the covariance matrix of this component are smaller than 0.1 (sigma=0.31 mas/yr) and it corresponds to more than 10 stars.
