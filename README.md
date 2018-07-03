# Brook90_R
Brook90 coded in R

### Manual for the Use of the BROOK90 R Implementation
This manual describes how to run the BROOK90 R implementation, based on the model by Federer, what files are necessary to download and what changes need to be done in the R-scripts.

#### Content

* [Overview of available files](#overview-of-available-files)
* [Download the data](#download-the-data)
* [Run the programm](#run-the-programm)
* [The output](#the-output)

#### Overview of available files
These files are available for usage:

  * Manual
      + instruction how to make the model work
  * Rmd-Files
      + as a documentation of the created scripts to help the understanding (to read on Github)
  * html-Files
      + to download and read the documentation offline
  * Data and R Code
      + necessary data (precipitation data, meteorological data) and written R scripts to run the programm
  * Catchment parameters
      + five .txt files where the characteristics of the catchment can be changed
  * Plot output
      + example plot of calculated values
  
#### Download the data
As the second step the files can be downloaded and unpacked. 

#### Run the programm
To run the programm in R, the MainProg.R script has to be opened. Important changes that have to be done are:

* put the data (meteorological and precipitatin data, .txt files) and R-Codes in the same folder, if it is not done yet
* change the SCRIPTPATH, where the R-scripts are located on your computer
* change the names of your input data (meteoFile, precFile), if you are not using the example
* change SCRIPTPATH_catchment, where the data of catchment parameters are located
* change catchment parameters in these files, if necessary:
    + canopy.txt
    + fixed.txt
    + flow_standart.txt
    + initial.txt
    + location.txt

After all changes are done, MainProg.R can be started by "Run from source". 

The next step is to open the script B90V4.R. At the end of this script there is a code to plot the output data. In this case precipitation, evaporation, calculated and measured flow are plotted. If other data should be shown, add or exchange the output data with "timeseries_" in its name. Finally B90V4.R can also be started with "Run from source" and then the model is running and producing the output.

#### The output
The programm calculates 24 time series of the water balance in the considered catchment as output of BROOK90. The table shows the explanation of the output data visible with the name "timeseries_..." and their corresponding shortcut:

Shortcut|Explanation
--------|-------------------------------------
adef    |available water deficit in root zone
awat    |available soil water in root zone
evp     |evapotranspiration
flow    |total flow
irvp    |evaporation rate of intercepted rain
isvp    |evaporation rate of intercepted snow
mesld   |measured flow
pint    |average potential interception for day
prec    |precipitation
ptran   |average potential transpiration rate for day
rfald   |rainfall rate
rintd   |rain interception
rnet    |rain reaching soil surface
rthrd   |rain throughfall
sfald   |snowfall
sintd   |snow interception
slfld   |input to soil surface
slvp    |soil evaporation
smltd   |snowmelt
snow    |water equivalent of snow on the ground
snvp    |evaporation from snowpack
sthrd   |snow throughfall
swat    |total soil water in all layers
trand   |transpiration

As mentioned in [Run the programm](#run-the-programm), all of this time series can be plotted if you add or exchange time series at the end of the script "B90V4.R".
