# Datasheet Template

As far as you can, complete the model datasheet. If you have got the data from the internet, you may not have all the information you need, but make sure you include all the information you do have. 

## Motivation

- The dataset was collected to be able to detect early-stage heart disease as well as for generate predictive machine-learning models.
- The dataset was contributed by Bhanu Prakash Doppala and Debnath Bhattacharyya on Mendeley and uploaded on Kaggle by Jocelyn Dumlao. 
- There is no information about the specific hospital where the data was collected or who funded the data collection. 
 
## Composition

- The dataset comprises of some demographic information (age, gender), results from medical tests including blood samples (serum cholesterol levels, fasting blood sugar), resting blood pressure, maximum heart rate reached, exercise induced chest pain (angina), type of chest pain, results from electrocardiogram (resting ECG results, old peak, slope), number of major blood vessels.
- There are 1000 patients in the dataset
- There is no missing data but the entries have some anomalous data
- The data doesn't contain information which will be considered confidential. 

## Collection process

- The data was collected from one of the multispecialty hospitals in India.
- There is no information about the sampling strategy or the duration. 

## Preprocessing/cleaning/labelling

- Data was processed to create categories for various features based on medical information (e.g., category of pain, normal or abnormal levels of certain parameters, etc.).
- There is no raw data available.
 
## Uses

- The dataset could be used to find features which are most associated with heart disease (e.g., univariate statistics). 
- There are two features which have anomalous data. It is important to either get the accurate data if using them for modelling or to impute/exclude to avoid inaccuracies in future analyses. I have excluded them from my analysis.

## Distribution

- The dataset is distributed under CC0: Public Domain license.

## Maintenance

- Jocelyn Dumlao maintains the dataset on Kaggle. 

