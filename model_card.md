# Model Card: Heart Disease prediction

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description
The presence or absence of heart disease is predicted using a Losgitic regression model containing five input features. The model parameters (coefficients) and formulae is given below:

The probability of presence of heart disease is given by solving the following equation:  
<br>
$\ln \Big(\frac{p}{1-p}\Big) = b_0 + b_1*scaled\_gender + b_2*scaled\_chestpain + b_3*scaled\_restingrelectro + b_4*scaled\_oldpeak + b_5*scaled\_slope$

$ p = \frac{1}{1+exp(b_0 + b_1*scaled\_gender + b_2*scaled\_chestpain + b_3*scaled\_restingrelectro + b_4*scaled\_oldpeak + b_5*scaled\_slope)}$

where, $b_0 = 3.1856708$, $b_1 = 0.67344694, b_2=1.10716387,b_3=0.84976867,b_4=-1.28893841,b_5= 3.84886661$ <br><br>
<b>*Please note that the features should be scaled prior to prediction using the same scaling factor which was derived from the training set.</b><br><br>
If $p>0.51$ then the individual is likely to have heart disease. 

**Input:** Describe the inputs of your model 
The final model 
**Output:** Describe the output(s) of your model

**Model Architecture:** Describe the model architecture you’ve used

## Performance

Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on. 

## Limitations

Outline the limitations of your model.

## Trade-offs

Outline any trade-offs of your model, such as any circumstances where the model exhibits performance issues. 
