![2ndCapstone](https://user-images.githubusercontent.com/67496237/98881458-eac0ac80-243e-11eb-9b93-d0d8406703f9.png)

A regression model built solely for 3DMark's Fire Strike.

## Summary

This project aims to project predictability through a regression model on 3DMark's Fire Strike benchmarking tool. Using the same scraper to gather similar data for my [previous research](https://github.com/caesarlindog/AMDvIntel3DMark), the only stark difference is the size of the data set along with the GPU scope now expanded to the currently-available Nvidia Turing SKUs (RTX 30XX). The ultimate goal for this project beyond this description would be to output a model that can be used to predict 3DMark Fire Strike scores with a set CPU, GPU, and RAM along with their respective metrics and clockspeeds. The limitation does not stop at available hardware - once optimized and tested, it will be also able to predict scores with future or upcoming hardware with an acceptable accuracy and minimized variance.

## Rationale

Benchmarking is a one-off solution a lot of consumers and corporations use to gauge if their system is performing within acceptable margins. Not only is it time-consuming, but it demands more than veritable notetaking with regards to hardware fluctuations. Removing that barrier will allow users to have more time in choosing other components and potentially not wanting to run any benchmarking tool as a baseline for stock performance. To add, 3DMark's data is publicly available. It is currently the most accessible out of the tools available for end-users albeit its imperfections in handling unfinished runs and lack in hardware metrics beyond clock speeds. That said, scalability and generalization is the main goal for the scraper I made solely for 3DMark. It is meant to continuously collect data while also taking into consideration future APIs 3DMark will be adding as part of its currently-supported suite. If the data holds up without bias, the scraper can be easily modified for other benchmarking tools provided the same data can be collected from each result.

## Process

Latest data collected are from 11.07.20. A new data set with GPUs outside Nvidia's RTX 3000 series is bound to added sometime soon without certainty.

The absence of any 3DMark data collated and formatted for this research prompted the creation of a scraper. I will not be adding in the scraper any time soon on this repository since it still is being continuously refactored.

Due to some faulty results caused by prematurely-ended runs, EDA took out a lot of the results that net a 0 score. Dimensionality reduction was done manually by removing all final score-related metrics like CPU score and GPU score along with those that presented a correlation coefficient of over 0.8.

Categorical features were one-hot encoded and numerical features were scaled.

Regression models used for initial comparison were XGBoost, Random Forest Regressor, and KNN Regressor.

## Changelogs

n/a

## Stack

Research is in Python on Jupyter Notebook.
Data was collected in Python with BS4.
Methods used: imputation by means, one-hot encoding, standard scaling, regression modeling, hyper-paramter tuning.
Models used: XGBoost, Random Forest Regressor, KNN Regressor
