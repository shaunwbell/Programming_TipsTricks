Software Readme
=============

Software
--------

MAMP (or other webserver stack)  / MariaDB
Sublime (or other text editor)   
GitHub desktop (alternative to managing git client)
Mercurial (TortoiseHG)   
QGIS (or other GIS tool)   
VLC   
Panoply  (netcdf visualization tool from NASA-GISS)

#### R/Rstudio
- CRAN
- ggplot2
- kohonen (SOM analysis)

#### ODV
- cmoceans colormap addons
- topographic addons

#### anaconda python   2.7/3.6/3.7
***Python 2 will be depricated in 2020 with many packages going only python 3 before then***
+ conda-forge as primary repo
- netcdf4
- matplotlib
- xarray
	- salem (geo-subsetting)
- pandas
- yaml
- basemap (dev and highres from conda-forge)
- cartopy
- gsw (TEOS-10 seawater standard)
	- GSW-python ***python3 only***
	- python-gsw ***deprecated***
- seawater (EOS-80 standard) ***python2***
- ctd
- cmoceans (colormap)
- udunits2
- pymysql
- pywget
- ephem
- geomag (magnetic declination calculator... WMM files are 2010 but need to be updated - this is done on github)
- mysql-connector
- pygc (a great circle calculator)
- pysftp *POC for conda-forge*
- pyserial *POC for conda-forge*
- erddapy [https://pyoceans.github.io/erddapy/quick_intro.html] ***python3 only***
- zeep (python soap client)
- gmt-python (GMT - Generic Mapping Tools wrapper) ***python3 only*** _dev project_
- jupyter lab ***see additional info below***

###### JupyterLab
***extensions***
- holoviews/geoviews
- geo.json renderer
- markdown renderer (native?)
- netcdf viewer
- github integration

##### PanGEO - python
Open Source platform for big data geoscience http://pangeo-data.org/
- xarray , pandas
- matplotlib
- numpy , dask
	- siphon (unidata data ingest - install via pip)
	- erddapy (erdap data ingest)

##### mercurial repo
UH-software https://currents.soest.hawaii.edu/hg/pycurrents/

##### pip
- calmap
- jupyter ***deprecated for now***
	- rise (jupyter-slideshow)
	- jupyter_nbextensions_configurator (extensions)

#### brew
- coreutils
- ffmpeg
- imagemagick
- ssh-copy-id
- pandoc
- cmake
- qgis
- tomcat

#### npm
- dygraphs
- bootstrap
- datatables
- leaflet

### ERDDAP Service
- needs tomcat
- java 1.8
- (ERDDAP files should be in /usr/local/Cellar/tomcat/{version}/libexe/)

### Testbed Software
- Docker?

Backups
-------

#### ecoraid data archive
- old archive
- new style archive
- documentation
- argo data
- iphc (halibut commision)

shaun bell internal pavlof webserver

**omit following files**  
- ferret.jnl* (ferret files)

from github  
- python routines
- rscripts
- general utilities

FOCI-Imagery and Graphics  
- From Karen Birchfield post retirement (2017)

Project Data Synthesis List
---------------------------

+ ITAE/PITAE
	- 2018 : Prawler Buoy (Bering, St Matt's), Popup Buoys
	- 2017 : Prawler Buoy (Bering, Chukchi), Oculus Glider
	- 2016 : Prawler Buoy, WaveGlider, Saildrone
	- 2015 : Prawler Buoy, WaveGlider, Saildrone
+ ArcticHeat
	- 2018 : XBT/AXCTD/ALAMO_FLOATS
	- 2017 : XBT/AXCTD/ALAMO_FLOATS
	- 2016 : XBT/AXCTD/ALAMO_FLOATS
+ NPRB_WarmEvent
+ Rusalca
+ SailDrone (2015 Bering Deployment)
+ Acrobat
	- 2016 Arctic Deployment
	- 2017 Bering Deployment

Local Only
----------

ancillary data records

SSH Copy and SSH Keys
---------------------

CMD Line Tips
-------------

Compare the contents of folder1 to folder2
	`diff -arq folder1 folder2`

Update existing installed packages with Brew Cask
	`brew cask list | xargs brew cask reinstall`

refresh git repository after files have been initially committed (often due to new .gitignore file)
	`git rm -r --cached .`
	`git add .`
	`git commit -m "gitignore updated and working"`


Data Access, Archive, Distribution Map  
--------------------------------------

***Access, ownership, redundancy, discovery***

Github/Git - Versioning and software creation (even one-use scientific scripts)
GoogleDrive - Archive and community access of digital records and media   
+not currently primary resource but soon to be
RaidStorage - (currently EcoRAID) - large redundant disk for archive of data and data access  
+primary data storage
ERDDAP - DataServer (group and lab wide versions) prevents direct raid access for final data streams
Webserver - Pavlof (local information of group interest and visualizations)
Webserver/MariaDB - Access to generation of digital records (mooring and ctd)   

ERDDAP Tips/Good Sources
------------------------

to start - `catalina start`

Alamo Floats
GOES Data
VIIRS/MODIS

