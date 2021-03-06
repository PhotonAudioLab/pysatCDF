# pysatCDF
[![Build Status](https://travis-ci.org/rstoneback/pysatCDF.svg?branch=master)](https://travis-ci.org/rstoneback/pysatCDF)
[![Coverage Status](https://coveralls.io/repos/github/rstoneback/pysatCDF/badge.svg?branch=master)](https://coveralls.io/github/rstoneback/pysatCDF?branch=master)
[![DOI](https://zenodo.org/badge/51764432.svg)](https://zenodo.org/badge/latestdoi/51764432)

Self-contained Python reader for NASA CDF file format

Uses standard and extended Fortran CDF interfaces to load Common Data Format (CDF) files into Python.

# Example
```
import pysatCDF
with pysatCDF.CDF(filename) as cdf:

    # All variable data loaded into dictionary in .data
    cdf.data
    data = cdf.data[name]
    # Attributes dictionary
    cdf.meta
    attribute = cdf.meta[name][attr_name]

    # CDF variable information available by name
    cdf[name]

    # Data access similar to other packages
    data = cdf[name][...]
    attribute = cdf[name].attrs[attr_name]

    # Export data to pysat data and metadata format
    data, meta = cdf.to_pysat()
```

# Installation
Actual CDF loading is performed by the [NASA CDF libraries] (http://cdf.gsfc.nasa.gov/html/sw_and_docs.html) 
which are included with pysatCDF.

To install pysatCDF
```
git clone https://github.com/rstoneback/pysatCDF.git
cd pysatCDF
python setup.py install
```

# Testing
pysatCDF has been tested on Mac OS X and Ubuntu 15.04. Support is included for building on windows if the mingw environment is present. 

# Motivation
Provide simple, robust access to CDF data in Python and simplify adding instruments to [pysat](https://github.com/rstoneback/pysat).
