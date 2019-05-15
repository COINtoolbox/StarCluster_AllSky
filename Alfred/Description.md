# Results from Alfred

## Method 
I have applied the methodology I developed in the framework of my PhD thesis. You can find an in depth description in Castro-Ginard et al. 2018, and the application of this methodology to a region similar to the region of this challenge in Castro-Ginard et al. 2019 (already accepted in A&A and soon in arXiv).
In fast, the methodology consists in two steps:
 * The application of DBSCAN in smaller boxes of LxL degrees. The size L of the boxes is optimised (together with the minPts parameter of DBSCAN) using a simulation of the Galaxy (GUMS, Robin et al. 2012) plus the adition of simulated open clusters (Luri et al. 2014). The other DBSCAN parameter, epsilon, is computed automatically in each box.
 * An artificial neural network trained to recognise isochrone patterns in the CMD. It is able to distinguish between real open clusters and statistical clusters, so it cleans from false positives.

## Results
The results depend on the criteria adopted to match one candidate to one known listed open cluster.
In this case, I made a two level identification: one positionally and one using the 5 astrometric parameters.
 * Positionally, I consider that a candidate is matched to a known object if its centres lie within a circle of 0.5 degrees. This way I can find 234 out of the 268 known objects, 87%.
 * Using the 5 astrometric parameters, I consider a candidate matched to a known object if the previous condition is fulfilled and mean parallaxes and proper motions differ by less than two sigma. In this case I find 208 known open clusters, 77%. 

The total number of candidates that I find is 789. There are two main reasons for the high number of clusters found: 
 * DBSCAN is run over several optimal pairs of (L,minPts), the identification of the same cluster found within all the pairs is done using the same conditions explained previously, however this may not be enough. 
 * The low complexity of the ANN.

## File description
 * CastroGinard18.txt: summary of the results.
 * Candidates.csv: Candidates found, columns are: [clusterN,l,b,parallax,pmra,pmdec,l_std,b_std,parallax_std,pmra_std,pmdec_std,Nfound]
    * Nfound: number of times one candidate is found within the explored optimal parameters. Note that this number may be larger than the number of explored parameters, the reason for this is that one cluster may be found by its substructures. The higher this number, the more reliable the cluster is.  
