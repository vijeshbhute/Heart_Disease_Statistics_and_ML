# PROJECT TITLE
Data exploration, analysis and prediction of presence/absence of heart disease in patients

## NON-TECHNICAL SUMMARY
Heart disease is a leading cause of death worldwide. There are various tests which are used to diagnose heart disease (e.g., electrocardiogram (ECG)) which can give several measurements. This data can be used to predict with certain accuracy whether someone has heart disease or not. The prediction accuracy can be increased by incorporating more details such as gender, questionnaires, etc. This project aims to develop a prediction model which is also interpretable so that the predictions can be explained easily by clinicians. 

## DATA
This project analyses cardiovascular disease dataset cotaining 12 features for 1000 patients from one of the multispecialty hospitals in India. The 12 features include information such as gender, resting BP, ECG results, etc. For each patient, the information about presence or absence of heart disease is provided in the last column called 'target'. 
The data was imported from Kaggle and can be found here: https://www.kaggle.com/datasets/jocelyndumlao/cardiovascular-disease-dataset/data
Citation for the data source: Doppala, Bhanu Prakash; Bhattacharyya, Debnath (2021), “Cardiovascular_Disease_Dataset”, Mendeley Data, V1, doi: 10.17632/dzz48mvjht.1
## MODEL 
I have started by exploring the data for inaccuracies or anomalies. I identified couple issues in the dataset and performed data cleaning to select the patients with accurate information. <BR><BR>
I next performed univariate statistical analysis to identify if there is any relationship between each feature and thet target. But, none of the single features explain the presence or absence of heart disease very well. <BR><BR>
So, finally, I applied machine learning to develop models which can predict this with high accuracy. I performed feature selection to identify the most relevant features which lead to high accuracy using backward selection method. I compared various models and decided to go with Logistic regression model due to the relatively small size of dataset, model's high accuracy as well as interpretability. <BR><BR>
After tuning hyperparameters, I also optimised the threshold for cut-off probability to further increase the prediction accuracy on the test set. 

## HYPERPARAMETER OPTIMSATION
Logistic regression has several hyperparameters including regularisation strength (inverse of this is represented by 'C'), random_state, and solver type for optimisation. I decided to optimise 'C' and solver type to identify the hyperparameters which lead to highest test set accuracy. 

## RESULTS
Feature selection identified 5 features (gender, chest pain, resting ECG result, oldpeak and slope) which can lead to high prediction accuracies. The best Logistic regression model is able to predict the presence/absence of heart disease with an accuracy of 94.81%. 

## SUMMARY
<ul>
    <li>Data exploration identified several individuals for whom serum cholesterol was 0. These individuals were excluded from analysis</li>
    <li>Data exploration also revealed several individuals for whom the slope was specified to be 0 which is not one of the possible choices. These individuals were also excluded from the analysis.</li>
    <li>Conducted correlation analysis and univariate logistic regression as well as chi square tests to identify significant relationships between numerical as well as categorical features and the target (absence of presence of heart disease) which is a categorical feature. </li>
    <li>Categorical features which were significantly associated with target (based on $\chi ^2$ test and a significance threshold of 0.05) were:
        <ul>
            <li> slope </li>
            <li> chest pain </li>
            <li> no. of major vessels </li>
            <li> resting ECG result </li>
            <li> fasting blood sugar </li>
            <li> gender </li>
        </ul>
    </li>
    <li> Numerical features which were significantly associated with target (based on logistic regression and AUC threshold of 0.6) were: <ul>
        <li>resting BP</li>
        <li>serum cholesterol</li>
        <li>max heart rate</li>
        </ul>
    </li>
    </ul>
<b>Machine learning summary</b>
    <ul>
    <li>Univariate statistics doesn't explain complex relationships between the target and features. Therefore, I applied machine learning to investigate these complex relationships. Since the application is relevant for clinical field, I am interested in interpretable models. </li>
    <li>I used 10-fold cross-validation to assess the model performance on the training set.</li>
    <li>There are 12 features, so I wanted to identify the relevant features for the model. I used two methods: <ul>
        <li> Logistic regression with Lasso regularisation: This forces the non-relevant features' coefficient to become 0. This helped in ruling out one of the features. </li>
        <li> Backward elimination: This identified a set of 5 features which also result in similar accuracy as the 12 feature model. </li>
        It is important to scale the features before performing Logistic regression. Training data was scaled using autoscaling method and the same parameters were used for scaling test set.</ul>
        <li> I then compared the performance of logistical regression model with 5 features with various other models including k-nearest neighbour classifer, support vector classifier (linear as well as kernel (rbf)), naive bayes classifier, decision tree classifier and random forests classifier. </li>
    <li>Logistic regression outperformed several of these models in terms of test set accuracy and also benefits from interpretability so selected this further for hyperparameter tuning.</li>
        <li> Tuned 'C' (Inverse of regularization strength) and solver hyperparameters for Logistic regression and built the final model. </li>
        <li> The key features* of this model are: 
            <ul>
                <li>slope</li>
                <li>oldpeak</li>
                <li>chest pain</li>
                <li>resting ECG result</li>
                <li>gender</li>
                *Please note that the features should be scaled prior to prediction using the same scaling factor which was derived from the training set.
            </ul>
        </li>  
    <li> Optimised the threshold probability of the model to maximise the test set accuracy. </li>
    </ul>

