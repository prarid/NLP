## Biography Based Nationality Prediction

This project aims to predict an individual's nationality based on information from her/his Wikipedia biography, i.e., text analysis based multiclass prediction/classification. It consists of the following key stages:

### Text Processing
Approximately 319K individual biographies were analyzed which cover more than 20 distinct nationalities. spacy, nltk, regex and sklearn libraries were used to process the text based data prior to modeling.
* <b>Part 1 - Cleaning the Target (Nationality) Field:</b> Three approaches were considered to clean the target field;
  1. Prior Knowledge Based Transformations,
  2. Spacy Named Entity Recognition Based Transformations utilizing geographical information, and
  3. a combined approach
     
* <b>Part 2 - Cleaning the Biography Field:</b> Typical text based processing consisting of removing stopwords, alpahnumerics and other noise, as well as tokenization and lemmatization is applied to the biographies in the dataset. Some common words seen for the top three nationalities are:
     
<p align="center"><img src="NationalityPrediction/Images/american_wc.png" width = 500>
<p align="center"><img src="NationalityPrediction/Images/british_wc.png" width = 500>
<p align="center"><img src="NationalityPrediction/Images/indian_wc.png" width = 500>
    

### Prediction Modeling
A logistic regression based model was used to predict the nationalities frome the text based biography inputs. Note: the focus of this project is more on gaining experience with text processing rather that classification modeling (which I have covered in other projects), so only logisitc regression is used in this project. Some potential other models that could be explored include Multinomial Naive Baiyes or Random Forest Classification, for instance.
   * <b>Part 1 - Classification Model on the Unbalanced Dataset:</b> The logistic regression model has an aggregate macro f1 score of .87 and micro f1 score .89 
<p align= "center"><b>Confusion Matrix - Unbalanced Dataset</b></p>
<p align="center"><img src="NationalityPrediction/Images/LogReg_ConfMatrix2.PNG" width = 700>

 * <b>Part 2 - Balancing the Dataset:</b> imblearn is used to undersample the dominant classes (nationality is "american" or "british"), followed by SMOTE to oversample all minority classes, such that all classes have 30Krecords each in the dataset. The logistic model on this updated dataset has an aggregate macro f1 score of .85 and micro f1 score .85. While the aggregate scores remain largely the same, we can see in the figure below that minority class performance improves (e.g, "irish")
<p align= "center"><b>Confusion Matrix - Balanced Dataset</b></p>
<p align="center"><img src="NationalityPrediction/Images/LogReg_Bal_ConfMatrix2.PNG" width = 700>

The code files and other relevant details can be found [here](https://github.com/prarid/BiographyBased_NationalityPrediction/blob/main/NationalityPrediction/WikiNationalityPrediction.ipynb)
