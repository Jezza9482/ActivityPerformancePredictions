## Activity Performance Predictions ReadMe

By Jeremy Roscoe Nov 2017  

  * Note that all code was written and run on a Macbook Pro using a 2.4GHz Intel Core i7 processor with R version 3.3.3 (2017-03-06) on a x86_64-apple-darwin13.4.0 platform using macOS Sierra version 10.12.6.  
  * All code used to create the report is present within the report including the relevant links to source data sets and studies.  
  * To view the completed HTML page of the report click [this link](http://htmlpreview.github.com/?https://raw.githubusercontent.com/Jezza9482/ActivityPerformancePredictions/master/APPredictions.html)  
  
#### Variables created:

  + **rawdat** ~ The raw downloaded dataset for use in training and cross validation  
  + **assessdat** ~ The raw downloaded dataset for use in final assessment of the predictive models  
  + **inTrain** ~ An indexing variable for partitioning data in an 80:20 split  
  + **trainInit** ~ 80% of *rawdat* indicated by *inTrain* to be further partitioned  
  + **validating** ~ 20% of *rawdat* not indicated by *inTrain* for validating purposes  
  + **inTrain2** ~ An indexing variable for partitioning data in a 75:25 split  
  + **training** ~ 60% of *rawdat* indicated by *inTrain* & *inTrain2* for model training  
  + **testing** ~ 20% of *rawdat* indicated by *inTrain* & not by *inTrain2* for cross validation  
  + **badindices** ~ A logical vector corresponding to columns unsuitable for use in the models  
  + **cl** ~ A clustering variable for use in parallel processing  
  + **fitcon** ~ The train control parameters to allow cross validation within model selection for each method as well as allowing parallel processing for time consuming processes  
  + **mod1** ~ The first model using *rpart* as the method  
  + **mod2** ~ The second model using *treebag* as the method  
  + **mod3** ~ The third model using *rf* as the method  
  + **mod4** ~ The fourth model using *gbm* as the method  
  + **gbmGrid** ~ A grid expansion variable allowing for adjustment of the interaction depth, number of trees, and shrinkage used in the *gbm* method  
  + **mod5** ~ The fifth model using *gbm* as the method with adjustments using *gbmGrid*  
  + **Acc()** ~ A function that takes a model as an argument, calculates predictions for the *testing* and *validation* datasets then returns the accuracies based upon the Training (In Sample), Testing, and Validating data sets as well as the mean of the two Out Of Sample datasets  
  + **a** ~ A temporary variable used by *Acc()* to hold the vector to be returned  
  + **pred** ~ A temporary variable used by *Acc()* to hold the prediction of the model on the *testing* set  
  + **predV** ~ A temporary variable used by *Acc()* to hold the prediction of the model on the *validating* set  
  + **assess2-5** ~ variables holding the predictions of models 2-5 for *assessdat*  
  + **b** ~ A dataframe containing the variable names, number of levels, class, and percentage of unusable cells for each of the 160 columns of the raw data set
  + **AccCompare** ~ A dataframe using *Acc()* for each of the original 4 models to compare the accuracies of each model  
  
Note that the variables used in the raw datasets can be viewed from the source, linked in the report or by clicking [here](http://groupware.les.inf.puc-rio.br/public/papers/2013.Velloso.QAR-WLE.pdf) 