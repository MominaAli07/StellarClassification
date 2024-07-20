# Celestial Object Classification
## Overview
The scientific study of celestial objects, phenomena, and the universe is known as astronomy. The exploration of the universe's origins and evolution, as well as the observation and study of stars, planets, moons, galaxies, and other celestial phenomena, are just a few of the many themes covered in this area.
Improving our knowledge of the properties and cosmic distribution of celestial objects is the main objective of this study. Our goal is to use data mining techniques to categorize stars, galaxies, and quasars according to their spectral features.
We used a variety of classification methods on the dataset, evaluating each one's accuracy-based performance.
# Dataset
We obtained the Sloan Digital Sky Survey (SDSS) dataset from Kaggle for this research. Each of the 100,000 observations in the dataset has 17 characteristics. Three distinct object kinds are included in the target feature, class:
*  Galaxy
*  Quasar (QSO)
*  Star

## Dataset Features

| Feature        | Description                                                   |
|----------------|---------------------------------------------------------------|
| Obj ID         | Object Identifier, the unique value that identifies the object|
| alpha          | Right Ascension angle (at J2000 epoch)                        |
| delta          | Declination angle (at J2000 epoch)                            |
| u              | Ultraviolet filter in the photometric system                  |
| g              | Green filter in the photometric system                        |
| r              | Red filter in the photometric system                          |
| i              | Near Infrared filter in the photometric system                |
| z              | Infrared filter in the photometric system                     |
| class          | Object class (galaxy, star, or quasar object)                 |
| MJD            | Modified Julian Date                                          |
| spec_obj_ID    | Unique ID used for optical spectroscopic objects              |
| run_ID         | Run Number used to identify the specific scan                 |
| rereun_ID      | Rerun Number to specify how the image was processed           |
| cam_col        | Camera column to identify the scanline within the run         |
| field_ID       | Field number to identify each field                           |
| redshift       | Redshift value based on the increase in wavelength            |
| plate          | Plate ID, identifies each plate in SDSS                       |

