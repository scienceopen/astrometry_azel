[![Zenodo DOI](https://zenodo.org/badge/19366614.svg)](https://zenodo.org/badge/latestdoi/19366614)
[![AstroPy](http://img.shields.io/badge/powered%20by-AstroPy-orange.svg?style=flat)](http://www.astropy.org/)
[![Xarray](https://img.shields.io/badge/powered%20by-xarray-orange.svg?style=flat)](http://xarray.pydata.org/en/stable/why-xarray.html)
[![Travis-CI](https://travis-ci.org/scivision/astrometry_azel.svg?branch=master)](https://travis-ci.org/scivision/astrometry_azel)
[![Coverage](https://coveralls.io/repos/github/scivision/astrometry_azel/badge.svg?branch=master)](https://coveralls.io/github/scivision/astrometry_azel?branch=master)
[![AppVeyor](https://ci.appveyor.com/api/projects/status/0hfbtk1om99mfy0o?svg=true)](https://ci.appveyor.com/project/scivision/astrometry-azel)

# Azimuth/Elevation converter for [Astrometry.net](https://github.com/dstndstn/astrometry.net)

Note: If you want to work with the intermediate steps (source extraction) or photometry, see my AstroPy-based 
[examples](https://github.com/scivision/starscale).

## Prerequisites

[Astrometry.net &ge; 0.67](https://scivision.co/setting-up-astrometry-net-program/)
or, use the [astrometry.net cloud service\--handy for Windows
users](http://nova.astrometry.net/upload)

Installation
------------

    python -m pip install -e .

### Astrometry.net index files

If you use astrometry.net on your PC, you may need to install the index
files and setup your config file to point at them:

    downloadIndex.py

Command line options
--------------------

\--h5 write az/el et al to HDF5 \--mat write az/el et al to .mat Matlab
save file \--png write az/el et al to PNG -h to see all the options you
can use

Examples
--------

### Astrometry.net installed on your PC:

    python PlateScaleFITS.py myimg.fits -c 61.2 -149.9 -t 2013-04-02T12:03:23Z --h5 --png

gives HDF5 .h5 with az/el ra/dec and PNG plots of the data. Both files
contain the same data, just for your convenience.

The 61.2 -149.9 is your WGS84 coordinates, 2013-04-02T12:03:23Z is UTC
time of the picture.

### wcs.fits from the Astrometry.net WEBSITE:

first rename wcs.fits to myimg.wcs:

    python PlateScaleFITS.py myimg.wcs -c 61.2 -149.9 -t 2013-04-02T12:03:23Z --h5 --png
