# Atmospheric_General_Circulation

Note 1 : This code was developed for educationnal purposes, and for French students. So the comments in the notebook are in French but the graphics and legends are in English.

Note 2 : If you have any comment/suggestion, if you find this code useful --> please send me an email : mailto:frederic.ferry@meteo.fr

The gridded data needed to run the notebook are NOT provided

Get the monthly data here :
- https://downloads.psl.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/omega.mon.mean.nc
- https://downloads.psl.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/uwnd.mon.mean.nc
- https://downloads.psl.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/vwnd.mon.mean.nc
- https://downloads.psl.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/omega.mon.mean.nc

Daily NCEP data are available here :
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/hgt.XXXX.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/air.XXXX.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/uwnd.XXXX.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/vwnd.XXXX.nc

Replace XXXX by the desired year. The code needs the 2000-2005 daily data. You will have to concatenate the yearly NCEP data in one file with NCO ncrcat command or CDO mergetime command:
- https://linux.die.net/man/1/ncrcat
- https://code.mpimet.mpg.de/projects/cdo/embedded/index.html#x1-930002.2.6

--> files z.nc, t.nc, u.nc, v.nc

--------------------------------------------------------------------------------------------------------------------------------------------------


Notebook 1 :
- Plot the zonal mean radiative budget from CERES data.
- Derive an analytic approximation of the radiative budget to highlight the radiative differential heating.
- Compute the required heat transport by the global circulation to compensate radiative differential heating.

![TOA_rad_budget_zonal_annual_analytic](https://user-images.githubusercontent.com/76565450/196165672-c83ad076-ba6a-4d8d-8cfe-d072f65c5645.png)

--------------------------------------------------------------------------------------------------------------------------------------------------


Notebook 2 : 
- Study the Hadley cell in vertical velocity and meridional wind fields
- Compute the Hadley Meridional Overturning Circulation from NCEP monthly reanalysis data

![psi_zmean_monclim](https://user-images.githubusercontent.com/76565450/162641912-96dcc725-e629-459b-b416-d241c12bb801.gif)

--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 3 :
- illustrate the difference between a zonal anomaly and a transient anomaly : $$z' = z-\overline{z}$$ ; $$z^* = z-[z]$$
- Demonstrate the decomposition : $$z=\overline{[z]}+\overline{z^*}+[z]'+z^{*'}$$

Notebook 4 :
- Study the stationnary anomalies from zonal mean of the geopotential field
- Compute the streamfunction from zonal and meridional winds and tudy the stationnary anomalies from zonal mean of the stremfuinction field

--------------------------------------------------------------------------------------------------------------------------------------------------




