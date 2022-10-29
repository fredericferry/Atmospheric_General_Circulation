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
- Study the Hadley cell in vertical velocity and meridional wind fields
- Compute and study the Mean Meridional Overturning Circulation

![wv_zmean_annual_climatology](https://user-images.githubusercontent.com/76565450/198851562-c410b6c6-ec63-482f-b464-d911add8ae71.png)
![psi_zmean_monclim](https://user-images.githubusercontent.com/76565450/198851564-851f9d7c-f401-4611-bc0f-a7e20bda990e.gif)


--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 4 :
- Illustrate the difference between a zonal anomaly and a transient anomaly
- Demonstrate that a field can be decomposed in 4 components (axisymetric and stationnary, transient anomaly of the zonal mean, non-axisymetric transient anomaly, stationnary anomaly of the zonal mean)
- Compute and decompose meridional transports of heat and momentum

![z2021-01-01](https://user-images.githubusercontent.com/76565450/198851586-c921c213-8e4e-49fc-bf9d-b48c6f47b78f.png)
![z_decomp_2021-01-01](https://user-images.githubusercontent.com/76565450/198851574-a27ccfe7-b4ac-43a8-9098-b46300d2691c.png)
![eddy_heat_flux_decomposition_2021-01-01-2021-03-31](https://user-images.githubusercontent.com/76565450/198851607-a9ecc754-208e-455f-b608-444a2f269385.png)


--------------------------------------------------------------------------------------------------------------------------------------------------

Notebook 5 :
- Study the meridional heat and momemtum fluxes by stationnary and transient eddies
![eddy_heat_flux_seasonal_era5](https://user-images.githubusercontent.com/76565450/198851622-2030ad18-95ea-494c-9cc8-1db1698780c0.png)
![eddy_momentum_flux_seasonal_era5](https://user-images.githubusercontent.com/76565450/198851627-c447f381-8cb6-4fdd-b85c-d11a9fd1d905.png)
![stat_heat_flux_seasonal_era5](https://user-images.githubusercontent.com/76565450/198851634-e85e4660-6519-49f2-b6d1-a225c9c85eeb.png)
![stat_momentum_flux_seasonal_era5](https://user-images.githubusercontent.com/76565450/198851638-368eff4c-07ed-46e0-96fc-d1ef189e0309.png)

