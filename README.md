
## Supervised Machine Learning and Credit Risk ##
--------
*Overview of the loan prediction risk analysis:*

>FastLending, a peer-to-peer lending services company wants to use machine learning to predict credit risk. Management believes that this will provide a quicker and more reliable loan experience. They also believe that machine learning will lead to a more accurate identification of good candidates for loans which will lead to lower default rates. In this situation, I will build and evaluate several machine learning algorithms to predict credit risk. 

**Techniques used:** 
- Oversampling: RandomOverSampler and SMOTE algorithms
- Undersampling: ClusterCentroids algorithm
- Combinatorial approach of over- and undersampling: SMOTEENN algorithm
- Predict credit risk: BalancedRandomForestClassifier and EasyEnsembleClassifier


Step 1: data cleaning + sorting into two groups

- features
- target

The features included everything except for "loan_status": 

<img width="1007" alt="features1" src="https://user-images.githubusercontent.com/106992995/205543853-486cee37-8047-4a60-af0c-9950246043bb.png">


The target group contained the "loan_status":

<img width="456" alt="y_loanstatus" src="https://user-images.githubusercontent.com/106992995/205544161-6afb077e-0a36-4959-bc22-bd928985021f.png">


Then, the “train_test_split” method from the scikit-learn library was used to split the data into 4 groups: X_train, X_test, y_train, and y_test.

<img width="637" alt="alg_split4" src="https://user-images.githubusercontent.com/106992995/205544760-f393c9bf-d2a6-46d0-8743-a8456591d1b6.png">




*Oversampling Results:*

The RandomOverSampler method, from the imbalanced-learn library, duplicates examples in the minority class of the training dataset. After using this method, there were 51,366 “low_risk” and 51,366 “high_risk”.

<img width="552" alt="RandomOversampling" src="https://user-images.githubusercontent.com/106992995/205545635-62f03267-ccb1-4da2-8aca-cde8d6e6b78d.png">

Next, the LogisticRegression model was used to “fit” the data using the scikit-learn library.

<img width="543" alt="LogisticReg" src="https://user-images.githubusercontent.com/106992995/205545677-6f81b8a1-1254-4d9e-9fa2-c1e819fdee6a.png">


Then, the balanced_accuracy_score were calculated

<img width="448" alt="balancedAccScore" src="https://user-images.githubusercontent.com/106992995/205545817-14ee2e23-ace0-4326-9dad-802fdce7f566.png">


Next, a confusion matrix was created from the scikit-learn library and then an “Imbalanced Classification Report” was calculated using the imbalanced-learn library method of classification_report_imbalaced

<img width="727" alt="confusionMatrix_ImbL" src="https://user-images.githubusercontent.com/106992995/205546045-151c325d-c6ea-4cee-99a0-fa0d54fdae45.png">

------------------

**SMOTE Oversampling**

The Synthetic Minority Oversampling Technique (SMOTE) method from imbalanced-learn library accomplishes this goal. SMOTE works by selecting examples that are close in features and drawing a line between the examples in the feature space and drawing a new sample along the line.

After using this method, similar to the RandomOverSampling method, there were also 51,366 “low_risk” and 51,366 “high_risk”.

<img width="889" alt="SMOTE" src="https://user-images.githubusercontent.com/106992995/205546474-a9e257ee-b18b-481f-9062-603478f8f1d8.png">


<img width="708" alt="O samp summary" src="https://user-images.githubusercontent.com/106992995/205546804-849f6389-995e-4ed7-8c5c-40fcc31bda28.png">

----------------------

**Undersampling**

Undersampling algorithms to determine which algorithm results in the best performance compared to the oversampling algorithms done above.

<img width="518" alt="ClusterCentroids" src="https://user-images.githubusercontent.com/106992995/205547601-9b950854-5fc0-45a0-a72d-f424811ef076.png">

After using the ClusterCentroids method on the data, there were 246 "high_risk" and 246 "low-risk".

<img width="706" alt="ClusterCSumm" src="https://user-images.githubusercontent.com/106992995/205547719-a26d6f0f-80f0-416a-8c32-54669ba222bb.png">




