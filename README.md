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

# Methodology
## Dealing with class imbalance
The SDSS dataset we considered suffered from a class imbalance problem. To deal with this class imbalance issue, we did both the down-sampling and up-sampling of our data to analyze which one performs better with machine learning models.
## Dealing with DImensionality
The SDSS dataset under consideration has 18 features. We employed different dimensionality reduction techniques to analyze the effects they had on the accuracy of the different models. PCA, LDA, and an autoencoder were each used on the models. For PCA, to determine the total number of components required to estimate the variance in data, we used a popular method called the Elbow Method. We plot the cumulative explained variance on the y-axis and the number of components on the x-axis and observe the point where, in the plot, the variance appears to slow down. The optimal components we selected are 10.
## Random Forest
A standard scalar was used to transform the feature values between 0 and 1. Where 0 is the mean and 1 represents the standard deviation. Also, for dataset division, an 80-20 split was created in which 80% is reserved for training while the rest of 20% is used for testing. 

Let's discuss the results obtained on each Random Forest. On original data, we achieved an accuracy of 0.9777 and with PCA, LDA, and AE on original data, the accuracy achieved was 0.9323, 0.9016, and 0.969 respectively. Similarly, Using Down-sampled data, we achieved accuracies of 0.9762, 0.9281, 0.8925, and 0.9668 on downsampling, PCA, LDA, and Ae respectively. Then on upsampling, we achieved 0.9926, 0.9743, 0.9461, and 0.9890 accuracies on upsampled data, PCA, LDA, and AE.
# Results

| Method            | Accuracy  |
|-------------------|-----------|
| Original Data     | 0.9777    |
| Downsampling      | 0.97626   |
| Upsampling        | 0.99268   |
| PCA Downsampling  | 0.92812   |
| PCA Upsampling    | 0.97493   |
| PCA Original Data | 0.93235   |
| LDA Downsampling  | 0.89255   |
| LDA Upsampling    | 0.94614   |
| LDA Original Data | 0.90165   |
| AE Downsampling   | 0.96689   |
| AE Upsampling     | 0.98903   |

### Particle Swarm Optimization (PSO)
Let's now discuss the results we obtained by optimizing Random Forest parameters using PSO. The parameters we optimized using PSO are the number of estimators of Random Forest and maximum depth. The range for several estimators was from 10 to 50 while the tree depth was from 1 to 5. 

We used only 5 iterations because the PSO was taking a lot of time. For the whole data, we also tried 100 iterations but eventually, we stopped the execution on the 4th day without getting any results. So we set iteration to be only 5 to estimate the results. On the original data, the PSO took 182 minutes and gave us an accuracy of 0.9591, and on the upsampled data PSO took 270 minutes and gave an accuracy of 0.9599 which was a very small increase as compared to the accuracy obtained on the original data. Then we also optimized the RF parameters on downsampled data and got an accuracy of 1 which was the maximum accuracy we achieved on the stellar classification dataset.
| PSO with RF      | No. of Iterations | Accuracy |
|------------------|-------------------|----------|
| Original Data    | 5                 | 0.9591   |
| Downsampled Data | 5                 | 1        |
| Upsampled Data   | 5                 | 0.9599   |

