# nextGEMS_hackathon_regridding
notebook comparing regridding methods for IFS data

This notebook was developed over the nextGEMS hackathon (Wageningen 14th-18th October). It is designed to work on Levante and compares the effects of different re-gridding methods on  small regions / variables with steep graidents. It runs on the IFS-FESOM historical run (approx 10 km) and uses two different intake methods, both developed for the Destination Earth initiative: the AQUA reader and the Generic State Vector (GSV) interface. 

The case study uses `mtpr' (precipitation rate) over the Canary islands. This variable was chosen as it's avaliabe both in the native IFS grid and as healpix zoom level 9 on the FDB. The method used to regrid between native to heaplix (done before storing on the FDB) is CDO - conservative.

Here we compare each re-gridding method to the native grid resolution. The code used for computing the error is based off: 
https://easy.gems.dkrz.de/Processing/healpix/plot-difference.html

This code on the website works for comparing native grid to healpix. We have modified slightly to include also a comparison with lat-lon.

Note we don't test bilinear and bicubic as they don't support repmapping from unstructured grids

I run this notebook using the AQUA environment :
https://github.com/DestinE-Climate-DT/AQUA/tree/main (then pip installed easygems)

Summary of all the errors from the different methods printed at the bottom
