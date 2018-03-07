Known Bugs/Conflicts
====================


Python
------

using conda libraries: (resolved around 2/1/2017)
	+ netcdf library (libnetcdf) 4.5.0 had an issue where ncdump wouldnt work -> 4.4.1.1
	+ cartopy (conflicts with brew install of geos). If it crashes kernal then check shapely ->1.5.17
	+ pandas and xarray had an issue with plotting 21.1 --> 20.0.3