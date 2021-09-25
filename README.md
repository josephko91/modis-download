# modis-load

This repository contains instructions and examples of how to batch download MODIS files.

# MODIS Basics
"MODIS (or Moderate Resolution Imaging Spectroradiometer) is a key instrument aboard the Terra (originally known as EOS AM-1) and Aqua (originally known as EOS PM-1) satellites ... It has a viewing swath width of 2,330 km and views the entire surface of the Earth every one to two days. Its detectors measure 36 spectral bands between 0.405 and 14.385 µm, and it acquires data at three spatial resolutions -- 250m, 500m, and 1,000m." ([NASA](https://modis.gsfc.nasa.gov/about/))

MODIS provides numerous land, ocean, and atmosphere products. Here we will focus on *MODIS land products*, but similar procedures can likely be followed for other products. A list of MODIS products can be found [here](https://modis.gsfc.nasa.gov/data/dataprod/).

A helpful overview of MODIS products can be found [here](https://lpdaac.usgs.gov/data/get-started-data/collection-overview/missions/modis-overview/). This link is particularly helpful for understanding the *naming convention* for MODIS products. 

# Downloading MODIS data
There are a number of different ways to access the MODIS data. This is just one method that I prefer.

## Step 1: Create/Log-in to NASA Earthdata
If you do not have a NASA Earthdata account, then you must first register [here](https://urs.earthdata.nasa.gov/users/new).

If you already created an account, [login](https://urs.earthdata.nasa.gov/).

## Step 2: Find the data you want
The next step is to use the Earthdata search tool to find the data product you want.

You can get to the search tool here: https://search.earthdata.nasa.gov/search or you can also get to it from the [Earthdata homepage](https://earthdata.nasa.gov/) by clicking "Find Data."

In the top left corner of the webpage, type in the MODIS product name and a list of matching collections will appear to the right. Below is an example using the MOD13A3 product (monthly vegetation indices).

<img src="images/fig1.png" width="700" alt="hi" class="inline"/>

Once you click on one of the matching collections, you should see a full list of all the product files. Below is what happens after we click on "MODIS/Terra Vegetation Indices Monthly L3 Global 1km SIN Grid V006" from the list of matching collections.

<img src="images/fig2.png" width="700" alt="hi" class="inline"/>

We see from the example above that there are 75,538 "granules" (i.e., data files) for this particular collection of the MOD13A3 data product. In order to narrow this down to the desired spatial/temporal scale, we need to filter the results in the next step (Step 3).

## Step 3: Filter the results
If you want the data for a particular *time period*, you can do this by either clicking on the small calendar icon, or using the "Temporal" filter tool under "Filter Granules" on the left side. For example, we can set the start and stop time such that only files for the year 2016 are selected (see below).

<img src="images/fig3.png" width="500" alt="hi" class="inline"/>

Click "apply" and you should now see only 3,493 granules returned from the search results. 

<img src="images/fig4.png" width="700" alt="hi" class="inline"/>

Next, you could apply a *spatial* filter if desired. One way to do this is to use the spatial extent selection tool (see below). 

<img src="images/fig5.png" width="300" alt="hi" class="inline"/>

You can use one of the geometric selection tools on the map to visually select the area of interest. For example, here we use the Rectangle tool to select the Los Angeles basin. 

<img src="images/fig6.png" width="700" alt="hi" class="inline"/>

(Tip: you can collapse/expand the search results panel to make the viewable area of the map larger.) 

<img src="images/fig7.png" width="700" alt="hi" class="inline"/>

## Step 4: Download the data
After applying a spatial and temporal filter for our MOD13A3 example, we see that we are left with 12 granules. It's a good idea to check at this point whether or not the number of granules makes sense. Since the LA Basin is fully enclosed within a single tile area, and our data product (MOD13A3) is a monthly product; the final granule count of 12 makes sense. But for example, if the spatial extent of our area of interest was split between two MODIS tiles, we would've ended up with 24 granules instead. 

<img src="images/fig8.png" width="700" alt="hi" class="inline"/>

When you are happy with the filtering, click "Download All." A new panel will appear; click "Download Data" (see below).

<img src="images/fig9.png" width="700" alt="hi" class="inline"/>

You will then be re-directed to a Download Status page, where you have a couple of options to download the files. At this point, it is a good idea to check that the list of files is correct in case a bug in the system is generating an incorrect list of file URLs. We see below in our example that there are 12 granulaes, and from the file names we can see that the correct product (MOD13A3) and tile area (h08v05) are being used. 

<img src="images/fig10.png" width="900" alt="hi" class="inline"/>

If you only have a few files, it could make sense to manually download each file. If you have a substantial number of files, you will likely want to use the Download Script that is provided by the website. 

<img src="images/fig11.png" width="900" alt="hi" class="inline"/>

Instructions for both Linux and Windows environments are provided on the website for further details. Here we show how the examples files are downloaded within a LINUX environment. 

First click "Save" and download the shell script file in your preferred directory. You will noticed the shell script file has a funny name. Rename it to "download.sh". 

You must change the permissions of the file to run the shell script. First change the directory to where your file is located. Then execute:
```
chmod 777 download.sh
```
Then run the script: 
```
./download.sh
```

You will be prompted to enter your username and password for your Earthdata account. Once you enter the credentials correctly, the download should commence in the current directory. 

<img src="images/fig12.png" width="700" alt="hi" class="inline"/>
