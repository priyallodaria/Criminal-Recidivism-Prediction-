# Criminal-Recidivism-Prediction

Background: Many jurisdictions around the United States are using risk assessment instruments (RAIs) in helping judges make bail decisions. 
Pre-trial RAIs are often statistical models that try to predict the likelihood that an individual will commit a crime if released on bail pending their court date.

Problem: For the past several years, the courts in Broward County, Florida have been using one of the Risk Assessment Instruments (COMPAS) to inform their decisions. 
In May of 2016 an investigative journalism team at ProPublica published a report that analysed whether COMPAS might be racially biased. 

Solution: We constructed a Risk Assessment Instrument for predicting two-year and violent recidivism for the courts in Broward County, Florida and evaluated the model’s predictive performance. 
We checked whether the Risk Assessment Instruments are equally predictive across race, age and sex categories. 
Also, we compared the model to the Risk Assessment Instrument currently being used by courts in Broward County, Florida in the COMPAS suite. Using a self-coded cross-validation function to assess model performance, we achieved 71% accuracy.

In the above project, there were total 53 variables and 7214 observations which was stored in the COMPAS.data. 

A. To determine the best classifier  
  1. We followed the following steps for different models to calculate the prediction error.  
      a. Split the data into test and training data  
      b. Fit the model on training data  
      c. Using the test data, we performed variable importance selection. 
  2. Now we had a list of variables in order of their importance. This set us up for forward subset selection on these variables.                    	
  3. We started with the first variable in order of importance and then fit random forest on the training data. We calculated the AUC for this model
  4. We continued the above approach for the first two, then first three and so on for all variables in order of importance and fit random forests and found the AUC.
  5. These AUCs were averaged out and correspond to the model. This approach minimized the variance of our model
B. To compare the instrument across race, sex and age, we calculated the area under the curve for each group and also plotted histograms.
C. To compare with the COMPAS tool, we plotted ROC curves, and confirmed our model performs better than the COMPAS tool. We also displayed a decision tree to compare the two models.
