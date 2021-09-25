# modis-load

This repository contains instructions and examples of how to batch download MODIS files in various formats.

# MODIS Basics
"MODIS (or Moderate Resolution Imaging Spectroradiometer) is a key instrument aboard the Terra (originally known as EOS AM-1) and Aqua (originally known as EOS PM-1) satellites ... It has a viewing swath width of 2,330 km and views the entire surface of the Earth every one to two days. Its detectors measure 36 spectral bands between 0.405 and 14.385 µm, and it acquires data at three spatial resolutions -- 250m, 500m, and 1,000m." ([NASA](https://modis.gsfc.nasa.gov/about/))

MODIS provides numerous land, ocean, and atmosphere products. Here we will focus on *MODIS land products*, but similar procedures can likely be followed for other products. A comprehensive list of MODIS products can be found [here](https://modis.gsfc.nasa.gov/data/dataprod/).

# Downloading MODIS data
There are a number of different ways to access the MODIS data. This is just one method that I prefer.

## Step 1: Create/Log-in to NASA Earthdata
If you do not have a NASA Earthdata account, then you must first register [here](https://urs.earthdata.nasa.gov/users/new).

If you already created an account, [login](https://urs.earthdata.nasa.gov/).

## Step 2: Find the data you want
The next step is to use the Earthdata search tool to query for the subset of data you want. 

You can get to the search tool here: https://search.earthdata.nasa.gov/search or you can also get to it from the [Earthdata homepage](https://earthdata.nasa.gov/) by clicking "Find Data."

