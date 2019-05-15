# Method

To tag a cluster candidate I follow a three step algorithm. 

1. I generate a rectangular tile pattern, apply a Gaussian kernel in RA and DEC and probabilsitly select stars inside the tile.
2. Run a tuned DBSCAN algorithm on the selected stars using 'ra', 'dec', 'pmra', 'pmdec', 'parallax' features. This step output a set of cluster candidates.
3. Merge cluster candidates which staisfy the following conditions: (1) angular seperation between their centers is < 1 deg (2) the absolution difference between mean proper motion of cluster members in RA and DEC is smaller than 
the variance proper motion of cluster members for at least one cluster.


# Discussion




# Output catalogs

The output catalogs consist of two datasets. One gives the properties of the identified cluster candidate and one is a list of cluster members.

"clusters_Arya_submission.csv" is the cluster catalog and "members_Arya_submission" is the cluster members.

The columns in the "clusters_Arya_submission.csv" are defined as following:

- ID           = cluster candidate unique Id
- medianRA     = median RA of the candidate cluster members
- medianDEC    = median DEC of the candidate cluster members
- madRA        = mad of RA of the candidate cluster members
- madDEC       = mad of DEC of the candidate cluster members
- regDRA       = span (max - min) of RA of the candidate cluster members
- regDDEC      = span (max - min) of DEC of the candidate cluster members
- medianPmRa   = median of the candidate cluster members proper motions in RA
- medianPmDec  = median of the candidate cluster members objects proper motions in DEC
- madPmRa      = MAD of the candidate cluster members proper motions in RA
- madPmDec     = MAD of the candidate cluster members proper motions in DEC
- medianPlx    = median of the candidate cluster members parallax
- madPlx       = mad of the candidate cluster members parallax
- nObj         = number of candidate cluster members
- possibleName = if the candidate cluster is a known cluster, the name of the known cluster


