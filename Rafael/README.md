# Method

## Very quick and dirty search

I mostly focused in speed, instead of purity. So the list requires some extra processing to merge redundancies. It time allows I will work on this tomorrow. Otherwise, cross-matching with other results will already clean-up my list. My script runs in 30 min over the entire region in my Desktop. 

### Steps

- MiniBatch Kmeans in regions of ~ 200,000 stars each. The search goes in bins of 2.5 in l, in 3 distinc regions of b. b >= -2.75 & b <= 2.75, b >= -10 & b <= -2.75 and b >= 2.75 & b <= 10. I search for a number of clusters ~ N/50, with batch size of ~ 0.25 Nclusters. 
- I remove any cluster with madPmRa and madPmDec > 0.175 and madPlx > 0.15


### Catalog

-  **rafael_fulll.cvs**: Entire output 
-  **Rafael_short_madPlx_l_0.1.csv**: Shorter version cutting madPlx > 0.1.
