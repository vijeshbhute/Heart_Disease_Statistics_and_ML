<script
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
  type="text/javascript">
</script>
# Model Card: Heart Disease prediction

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description
The model analyzed in this card predicts the presence or absence of heart disease based on patient information (demographic and medical information). The model can return either a classification (presence or absence of the heart disease) or it can also return the probability associated with presence of heart disease and absence of heart disease. The model's goal is to assist clinicians in making predictions based on non-invasive and cheap tests. 

On this page, you can learn more about how well the model performs.

**Input:** 
Demographic and medical information which is categorised or reported in a certain format. 
The five features are: 
<ul>
    <li>Gender: Assign <ul>
        <li>0 for female </li>
        <li> 1 for male</li>
        </ul>
    </li>
    <li>Chest pain: Assign <ul>
        <li>0 for Typical angina</li>
        <li>1 for Atypical angina</li>
        <li>2 for Non-anginal pain </li>
        <li>3 for Asymptomatic patient</li></ul>
    </li>
    <li>Resting ECG results: Assign<ul>
        <li>0 for Normal</li>
        <li>1 for Having ST-T wave abnormality</li>
        <li>2 for showing probable or definite left ventricular hypertrophy by Estes' criteria</li>
        </ul>
    </li>
    <li>Old peak: Value of ST (measure of abnormality in electrocardiograms) between 0 and 6.2.</li>
    <li>Slope: Slope of the peak exercise ST segment, assign<ul>
        <li>1 for upwards</li>
        <li>2 for flat</li>
        <li>3 for downward</li>
        </ul>
    </li>
</ul>

**Output:** The model returns a classification result/probability of whether the individual/patient has heast disease or not. 

**Model Architecture:** The probability of presence of heart disease is given by solving the following equation:  
<br>
$$\ln \Big(\frac{p}{1-p}\Big) = b_0 + b_1*scaled\_gender + b_2*scaled\_chestpain + b_3*scaled\_restingrelectro + b_4*scaled\_oldpeak + b_5*scaled\_slope$$

$$ p = \frac{1}{1+exp(b_0 + b_1*scaled\_gender + b_2*scaled\_chestpain + b_3*scaled\_restingrelectro + b_4*scaled\_oldpeak + b_5*scaled\_slope)}$$

where, $b_0 = 3.1856708$, $b_1 = 0.67344694, b_2=1.10716387,b_3=0.84976867,b_4=-1.28893841,b_5= 3.84886661$ <br><br>
<b>*Please note that the features should be scaled prior to prediction using the same scaling factor which was derived from the training set.</b><br><br>
If $p>0.51$ then the individual is likely to have heart disease. 

## Performance

Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on. 

## Limitations

Outline the limitations of your model.

## Trade-offs

Outline any trade-offs of your model, such as any circumstances where the model exhibits performance issues. 
