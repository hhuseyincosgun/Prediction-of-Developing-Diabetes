## <b><span style='color:#F1C40F'>1 |</span> About Dataset</b>

### <b><span style='color:#F1C40F'>Context</span></b>

The data used in this study originates from the **National Institute of Diabetes and Digestive and Kidney Diseases**. The main goal of this dataset is to predict the presence or absence of diabetes in patients, utilizing specific diagnostic measurements present in the dataset. Strict criteria were applied to choose these cases from a larger database. Specifically, all individuals included in this dataset **are female, at least 21 years of age**, and of Pima Indian descent.

### <b><span style='color:#F1C40F'>Who is Pima Indians ?</span></b>
"The Pima (or Akimel O'odham, also spelled Akimel O'otham, **"River People"**, formerly known as Pima) are a group of Native Americans living in an area consisting of what is now central and southern Arizona. The majority population of the surviving two bands of the Akimel O'odham are based in two reservations: the Keli Akimel O'otham on the Gila River Indian Community (GRIC) and the On'k Akimel O'odham on the Salt River Pima-Maricopa Indian Community (SRPMIC)." Wikipedia

### <b><span style='color:#F1C40F'>What is Diabetes ? </span></b>
Diabetes is a chronic medical condition that affects glucose metabolism. It occurs when the body either cannot produce enough insulin **(Type 1 diabetes)** or becomes resistant to insulin's effects **(Type 2 diabetes)**. Insulin is vital for regulating blood sugar levels, as it allows glucose to enter cells for energy. When insulin is impaired, glucose accumulates in the bloodstream, leading to high blood sugar levels. This condition can cause various symptoms such as frequent urination, excessive thirst, and fatigue. Diabetes requires careful management through medication, lifestyle changes, and monitoring to prevent complications that can affect the heart, kidneys, eyes, and nerves.

### <b><span style='color:#F1C40F'>Content</span></b>
The dataset comprises numerous medical predictor factors and one target variable, which is labeled as **"Outcome."** These predictor variables encompass the patient's history of **pregnancies, body mass index (BMI), insulin level, age, and other relevant parameters.**

### <b><span style='color:#F1C40F'>Purpose of the study</span></b>
- The main aim is to determine whether a patient is at risk of diabetes based on various characteristics and features.


### Dataset Attributes
- **Pregnancis** : Number of times pregnant
- **Glucose** : Plasma glucose concentration a 2 hours in an oral glucose tolerance test
- **BloodPressure** : Diastolic blood pressure (mm Hg)
- **SkinThickness** : Triceps skin fold thickness (mm)
- **Insulin** : 2-Hour serum insulin (mu U/ml)
- **BMI** : Body mass index (weight in kg/(height in m)^2)
- **DiabetesPedigreeFunction** : Diabetes pedigree function
- **Age** : Age (years)
- **Outcome** : Class variable (0 or 1) 268 of 768 are 1, the others are 0

------------------------------
### General evaluation:

1- All values containing 0(zero) except Pregnancies and Outcome are assigned "NaN".

2- The distribution of missing data was examined.

3- Missing values were replaced by median assignments according to the target variable.

4- Variable types were examined and whether encoding was required or not was analyzed.

5- 15%-85% iqr calculation was made for the outlier values and they were replaced with the lower and upper limit values.

6- Robust was preferred for the scaling method. It was preferred because it has IQR sensitivity.

7- The weight of minority samples was reduced using SMOTE.

8- The model was tested using different machine learning methods.

9- Feature importance analysis was performed.

10- Confusion Matrix and ROC Curve are output.


### Major Mistakes:

- Since we filled the lost values of **48.7% in the insulin variable with the median**, weight accumulation occurred at 2 points. As in our example, it distorted the distribution of the data, causing it to make biased estimates. We understood why we need to be more careful while filling in missing data. As can be seen in the feature importance graph, it seems that the result is significantly related to the target variable. This was the wrong approach. We have to deal with this properly.

- The newly created features did not produce effective results. The purpose of **extracting new features** is to get better results. But we could not observe this here.

- No problems were observed as there were not many outliers. However, a more effective solve against outliers should be done by paying attention to the class distributions.

