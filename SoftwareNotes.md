Backup Readme
=============

Software
--------

MAMP (or other webserver stack)  
Sublime (or other text editor)   
GitHub desktop (alternative to managing git client)   
QGIS (or other GIS tool)
VLC   

#### R/Rstudio
- CRAN
- ggplot2
#### ODV
- cmoceans colormap addons
- topographic addons

#### anaconda python   2.7/3.6
- conda-forge as primary repo
- netcdf4
- matplotlib
- xarray
- pandas
- yaml
- basemap (dev and highres from conda-forge)
- cartopy
- gsw (TEOS-10 seawater standard)
- seawater (EOS-80 standard)
- GSW-python ***python3 only***
- ctd
- cmoceans (colormap)
- udunits2
- pymysql
- wget
- ephem
##### pip
- calmap

#### brew
- googlechrome
- coreutils
- ffmpeg
- imagemagick
- ssh-copy-id
- pandoc
- cmake
- qgis
- wine
- gmt

#### npm
- dygraphs
- bootstrap
- datatables
- leaflet


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

Project Data Synthesis List
---------------------------

+ ITAE/PITAE
	- 2017 : Prawler Buoy, Oculus
	- 2016 : Prawler Buoy, WaveGlider, Saildrone
	- 2015 : Prawler Buoy, WaveGlider, Saildrone
+ ArcticHeat
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
