# AIstrophysics
The goal of this project is to infere the main physical parameters of stars (temperature, metallicity and surface gravity) from the measured spectra in the optical and infrared bands.

# DATA SETS
The training and testing data come from the "Sloan Digital Sky Survey (Data Release 14)"  (https://www.sdss.org/dr14/). We use roughly 50.000 source spectra of stars in each band.
To obtain the data, we first download the lists of available stellar spectra in both bands:

Optical data: 'https://data.sdss.org/sas/dr16/sdss/sspp/ssppOut-dr12.fits'

Infrared data: 'https://data.sdss.org/sas/dr16/apogee/spectro/aspcap/r12/l33/allStar-r12-l33.fits'

These lists contain the temperature, metallicity and surface gravity labels for each object, as well as all the necessary identifiers to download the spectra from the survey's webpage. All downloaded files are in .fits format, which is a common extension used in astronomy. 

After the preprocessing we end up with three clean data sets: 

1. Full infrared spectra
2. Full optical spectra
3. Cut optical spectra around the Fe line, this will be used to derive the metallicity.


# CODE

- Preprocessing_IR.ipynb: This notebook is used to download 50.000 spectra in the infrared band as .fits files, rearrange all data in a single .csv file, remove zeros, remove outliers and do the exploratory data analysis. The spectra in the infrared band is already normalize.

- Preprocessing_opt.ipynb: This notebook is used to download 50.000 spectra in the optical band as .fits files, rearrange all data in a single .csv file, remove zeros, normalize the spectra, remove outliers and do the exploratory data analysis. 

-random_forest.ipynb: We apply a random forest architecture to derive the stellar parameters.

-Regression_notebook.ipynb: We apply a Multilayer Perceptron. It consists of 4 hidden layers with 120 neurons each. 
