Known Bugs/Conflicts
====================


Python
------

~~
using conda libraries: (resolved around 2/1/2017)
	+ netcdf library (libnetcdf) 4.5.0 had an issue where ncdump wouldnt work -> 4.4.1.1
	+ cartopy (conflicts with brew install of geos). If it crashes kernal then check shapely ->1.5.17
	+ pandas and xarray had an issue with plotting 21.1 --> 20.0.3
~~

As of July, 1 -
    + gmt-python failing on downdraft.  Haboob not updated

Python 3.7 upgrade (end of June - 2018)
    Not all/any packages available yet 
    (pandas, xarray, numpy)

Demo jupyterlab for 3.6/3.7
    notebook compatibility?? (installed in 3.6 env, left notebook in 2.7)
    (numpy issues periodically)