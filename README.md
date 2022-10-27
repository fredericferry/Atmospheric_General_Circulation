# Atmospheric_General_Circulation

Note 1 : This code was developed for educationnal purposes, and for French students. So the comments in the notebook are in French but the graphics and legends are in English.

Note 2 : If you have any comment/suggestion, if you find this code useful --> please send me an email : mailto:frederic.ferry@meteo.fr

THIS CODE IS NOT FULLY FUNCTIONNAL, YOU WILL HAVE TO CODE SOME MISSING PARTS (THIS SHOULD NOT BE TOO DIFFICULT).

The gridded data needed to run the notebook are NOT provided

Get the CERES data here : https://asdc.larc.nasa.gov/project/CERES/CERES_EBAF_Edition4.1

Monthly NCEP data are available here :
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/air.mon.mean.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/uwnd.mon.mean.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/vwnd.mon.mean.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/omega.mon.mean.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.derived/pressure/shum.mon.mean.nc

Monthly ERA5 data need to be downloaded via Copernicus :
- https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels-monthly-means?tab=form
You will need to lower the horizontal resolution to 1 degree to have smalle files. It can be done with CDO (https://code.mpimet.mpg.de/projects/cdo) :
- cdo remapbil,r360x180 era5_v.1979-2018.mon.mean.nc era5_v.1979-2018.mon.mean.1deg.nc
- cdo remapbil,r360x180 era5_w.1979-2018.mon.mean.nc era5_w.1979-2018.mon.mean.1deg.nc

Daily NCEP data are available here :
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/hgt.XXXX.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/air.XXXX.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/uwnd.XXXX.nc
- ftp://ftp.cdc.noaa.gov/Datasets/ncep.reanalysis.dailyavgs/pressure/vwnd.XXXX.nc
Replace XXXX by the desired year. The code needs the 2015-2020 daily data. You will have to concatenate the yearly NCEP data in one file with NCO ncrcat command or CDO mergetime command:
- https://linux.die.net/man/1/ncrcat
- https://code.mpimet.mpg.de/projects/cdo/

--> files z.nc, t.nc, u.nc, v.nc

Get daily ERA5 data here :
- https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels?tab=form
You will have to download 4-hourly data and convert to daily means with CDO (https://code.mpimet.mpg.de/projects/cdo) :
- cdo daymean era5_z500_2021.nc era5_z500_daily_2021.nc

--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 1 (inspired by Stull : https://geo.libretexts.org/Bookshelves/Meteorology_and_Climate_Science/Book%3A_Practical_Meteorology_(Stull)/11%3A_General_Circulation/11.02%3A_Section_3-):
- Study the zonal mean radiative budget from CERES data.
- Derive an analytic approximation of the radiative budget to highlight the radiative differential heating
- Compute the required heat transport by the global circulation to compensate radiative differential heating.

![TOA_rad_budget_zonal_annual_analytic](https://user-images.githubusercontent.com/76565450/196165672-c83ad076-ba6a-4d8d-8cfe-d072f65c5645.png)
![TOA_net_transport_analytic](https://user-images.githubusercontent.com/76565450/196167592-85b7adb2-03a3-4783-b2f7-99496103b92b.png)


--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 2 : 
- Study zonal mean climatologies of the atmosphere from NCEP monthly reanalysis data

![theta_u_zmean_climatology](https://user-images.githubusercontent.com/76565450/196964611-b008b0eb-b826-4b67-bfad-30d54765d525.png)

--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 3 : 
- Study the Hadley cell in vertical velocity and meridional wind fields from NCEP monthly reanalysis data
- Compute and study the Meridional Overturning Circulation

![wv_zmean_annual_climatology](https://user-images.githubusercontent.com/76565450/198372627-21656062-27d1-4c24-92ae-cc54ef56a7bd.png)
![psi_zmean_monclim](https://user-images.githubusercontent.com/76565450/198372514-cf4f670e-3111-4d30-89f0-632526fac01b.gif)

--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 4 :
- Illustrate the difference between a zonal anomaly and a transient anomaly
- Demonstrate that a field can be decomposed in 4 components (axisymetric and stationnary, transient anomaly of the zonal mean, non-axisymetric transient anomaly, stationnary anomaly of the zonal mean)
- Compute and decompose meridional transports of heat and momentum

![z2015-01-01](https://user-images.githubusercontent.com/76565450/196910830-f5da86aa-c549-409c-91a3-10c6705d6963.png)
![z_decomp_2015-01-01](https://user-images.githubusercontent.com/76565450/196910873-a84fdbd7-37b5-4749-a6a2-bbfea19baf39.png)
![eddy_heat_flux_decomposition_2021-01-01-2021-03-31](https://user-images.githubusercontent.com/76565450/198373204-9f62818c-8825-47bb-a823-387ac8d24799.png)

--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 5 :
- Study the meridional heat and momemtum fluxes by stationnary and transient eddies

![eddy_heat_flux_seasonal](https://user-images.githubusercontent.com/76565450/196911112-fe611049-dbd3-473c-82f5-85d934a39076.png)
![stat_heat_flux_seasonal](https://user-images.githubusercontent.com/76565450/196911251-04d063fc-6aae-4da8-828a-c9cb85627920.png)
![eddy_momentum_flux_seasonal](https://user-images.githubusercontent.com/76565450/196969408-565af054-856f-442c-b980-edc088ab600e.png)
![stat_momentum_flux_seasonal](https://user-images.githubusercontent.com/76565450/196969490-36af6c18-98e6-483c-90f4-8a6f906df080.png)

