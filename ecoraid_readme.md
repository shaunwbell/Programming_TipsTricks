Ecoraid Structure
=================
Ecoraid is a raid array on a linux system that can be accessed via any system that can mount it as a drive.  Conventions below assume linux/unix standards.


Legacy (--2013):
----------------
Predominantly EPIC Standard (occasionally information is in ascii files or pre EPIC formats)

Structure of archive is heirarchical and in one of two categories:
- timeseries data
- profile data

### timeseries data ()
{ecoraid}/mooring_data/{year}/{mooringname}/data_file.nc
- ecoraid is the server path to the raid system
- year is the 4digit year
- mooringname is a descriptive name of each foci mooring 
    + [FOCI Maps](https://www.ecofoci.noaa.gov/maps)
    + [FOCI Mooring Names](https://www.pmel.noaa.gov/foci/foci_moorings/mooring_info/mooring_location_info.html) **Updated 2015**
    + Additional Mooring Names are on a [google drive](https://docs.google.com/spreadsheets/d/1LbfEu7XOGR3BwJmvDEeVFPBelU_o9JvZNOa5JRiSYc0/edit?usp=sharing) document **Current** 
- data_file.nc is a collection of additional, instrument/site specific information.  It is usually of the form yyMOR_iii_{dddd}m.nc
    + yy - 2digit year
    + MOR - mooring deployment id (a shortened version of the name, also available on the links above)
    + iii - instrument reference 
        * mt - microtemperature recorder
        * s39, s56 seabird temperature instruments (may also have pressure)
        * sc, s37 seabird CT instruments (may also have pressure, chlor, oxy, par)
        * rcm, an7, an9, an11 - anderraa current meters (may also have pressure, temperature, oxygen, turbidity, salinity)
        * par - photosynthetic active radiation
        * wcp/adcp/lrcp (vel, scal, ein) - 2D current/velocity data from Acoustic Doppler current profilers
        * ecf, eco, ws - chlorophyll/fluorometry from ecoLabs (may include turbidity, scattering in various wavelengths)
        * wpak sfc weather observations
    + dddd - depth of instrument in meters (usually epth corrected for deployment characteristics if known, nominal designed depth if not enough information is provided to isolate specific depth)
    + .nc - netcdf classic (v3) format

Data not in the format above is likely either data shared from another group and should be described in the header of that data set, or data directly from the instrument, described in that data format.  

Some data has been duplicated into the Modern structure described below (and is therefore redundant).

Modern (2013+):
---------------
Mostly EPIC but transitioning to CF/COARDS standards (2017+ for data from Prawler Platform, Glider Platform and Towed Vehicle Platforms)  Individual archived data files are mostly EPIC formatted netcdf files as described in the legacy framework above.  Non-EPIC files are CF compliant (or at least closer to CF compliance than EPIC is) and are identifiable by only having a single timeword.  The time will meet CF/COARDS standards and have similar attributes to the following:

        longname: date and time since reference time
        time_origin: '1900-01-01 00:00:00'
        units: 'hours since 1900-01-01T00:00:00Z'
    (the units on the time is allowed to fluctuate, as is the time origin as long as it is provided)

The Glider, Prawler and Towed Vehicle (as well as AlamoFloats and some underway data) are availabe as erddap data feeds.  Contact S.Bell for access.

Data Types
==========
In the archive, numerous types of files can be found.  These are usually either ascii flat files or binary files.  Raw data is as it came from the instrument, often without qc or full calibrations applied. 

### Archive Data Standards
- EPIC NetCDF
    + two time words
    + epic keys are defined by PMEL epic.key file
    + some epic keys are made up and not in epic.key file
    + inconcistent application of keys for similar data streams
        * (eg multiple keys for currents,chlorophyl. initial assignment depended on instrument used but this has been unenforced)
- CF/COARDS NetCDF
    + single time word
    + standard_names_when_available
    + more descritpive meta_data



Specific to Bering Season MAPPS
-------------------------------
