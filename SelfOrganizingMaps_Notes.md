Kohonen (SOM) Analysis Notes:
=============================

###Discussion Links
- https://www.shanelynn.ie/self-organising-maps-for-customer-segmentation-using-r/ (usage in customer analysis)
- http://ocgweb.marine.usf.edu/~liu/som.html (usage in geosciences)

r package

- https://cran.r-project.org/web/packages/kohonen/kohonen.pdf


### Usage in Oceanography/Meteorology

Spatial pattern recognintion - compare atmospheric features (pressure) to small scale more spiky features (precip-rate)

Hewitson & Crane (2002)

### Tunable Paramters

The specifics within the tunable paramters of SOM analysis are claimed to still be somewhat of a black box for oceanography/meteorologist using the method (Liu et all 2011) and a sensitivity analysis was performed to evaluate what paramters are of primary significance (Liu et all 2016)

- shape
- size
- neighbor geometry

Other fields and commments have suggested:
** Personal take... small SOM should capture primary modes... larger som will distribute into every mode if possible with an optimization of `5 * sqrt(n)` cells (Vesanto (2005)) and an avoidance of empty cells)**

- aim for 5-10 samples per node, empty cells are an indication of too big a map (https://www.shanelynn.ie/self-organising-maps-for-customer-segmentation-using-r/)

large number of soms cells needed for cluster interpretation  

#### Notes Per Bering Sea SOM Paper - Stabeno et al 2018
*** the SOM Bering Sea Ice Analysis of Stabeno et al 2018 has 36 years of 8 - 8day averages wich would be `5*sqrt(~300)` - which would be about 100 cells or possibly 10x10*** double this for the pressure/ice analysis ***

but our goal isn't to partition into every available pattern (unless we want to cluster) but to match general patterns.  We settled on a 3x3 (9cell) pattern.  Fewer cells didn't present enough differentiation in the structure of the ice and more modes began to provide maps that either didn't vary visually significantly from other patterns (and some indicated polyna information south of st lawrence but not sure what to make of that)

its exploratory visualization that we are most interested in.


choice of SOM shape/size isn't ellucidated - part of that black box nature.
existing shape/size choices seem to be 3x3 - 3x5 up to 4x6 in the literature presented in liu


In this paper we are using SOM as a data exploration and visualization technique and the tunable parameters have been chosen based on other SOM expolorations in oceanoography/meteorology.  It is acknowledged that the specifics within the tunable paramters of SOM analysis are claimed to still be somewhat of a black box for oceanography/meteorologist (Liu et all 2011) yet general analysis seems to allow some flexibility in the choice of parameters. Liu et al, 2016 performed a sensitivity analysis to evaluate what paramters are of primary significance and to provide guidance in parameter selection.  As we are interested in more general patterns, smaller mapsizes are more relevant.  We evaluated a 3x3, 4x2, 3x4 and 6x3 mapping.  The 3x3 and 4x2 mapping did not present significant differences in spatial patterns of each of the cells.  The 6x3 mapping did provide more detailed spatial patterns in addition to the patterns available in the 3x3 and 4x2 but the additional patterns came with significantly fewer samples per cell.  A balance of 4x3 was chosen to capture the general patterns without creating null patterns or overwhelming the author with an unmanageable number of patterns to interpret.