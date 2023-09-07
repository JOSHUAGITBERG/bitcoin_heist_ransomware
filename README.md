Synopsis:

    The following exercise leverages ensemble machine learning techniques to identify 
Ransomware addresses from within a dataset of bitcoin blockchain transactions. The models
are able to identify whether a given address is ransomware with 90% accuracy, and to identify 
whether it belongs to a specific Ransomware family to within 99% accuracy.  Given the proper 
data, the models generated here could be used by authorities to identify malicious addresses 
associated with ransomware, and be used by exchanges to keep malicious actors out of their 
ecosystem.

Ransomware Facts:

   Ransomware is a cyber attack vector that started demanding payment in bitcoin starting around 2013 with the emergence of “CryptoLocker”. Ransomware attacks have since become more common.  According to service provider AAG:
Ransomware attacks cost the US healthcare sector an estimated $7.8 billion in downtime alone in 2021
There were over 200 million ransomware attacks across the globe in the first half of 2022   
Ransomware accounted for around 20% of cyber breaches in 2022 

Bitcoin:

  Bitcoin is a cryptocurrency that allows direct exchange between digital addresses recorded on a blockchain.  Ransomware uses bitcoin to extract ransom because transactions are unregulated, digital, fast, global, irreversible, and anonymous.  However, because bitcoin has a publicly viewable ledger, we can analyze transactions to identify patterns indicating whether a given address or transaction maybe part of a ransomware network.  

Summary Findings:

   We built a random forest model that can identify a ransomware address with over 90% accuracy, and categorize it with 99% accuracy.  Assuming access to data similar to the information provided by Kaggle, the following models can be run as a daily batch process to alert authorities and exchange administrators to the potential of ransomware related activities. 

Methodology:

    Data Preparation: 

    The dataset was highly imbalanced, with only 2% of the data representing malware.  We took
two independent approaches to remedy this:

	Random Under Sampling:  

We combined all of the malware data with a random sample of just 2% of the remaining data set to create a balanced data set of malware and non-malware.  

	Near Miss Controlled Under Sampling:  

We used IMBLearn’s Near Miss library to perform controlled under sampling on the dataset.  Near Miss selects samples of non-malware samples with the smallest average distance to the closest malware sample. Because the distances between samples are minimized, the dataset is optimized for machine learning. In our example, Near Miss out performed random under sampling by 12-20%, as measured by cross validated F1 scores.  

	Synthetic Data Generation with Smote:

	SMOTE results were excluded from this notebook.  We did consider using SMOTE to
generate additional, synthetic training data. However, SMOTE datasets of ~50K samples scored
poorly (F1 ~50%).  When we generated a SMOTE dataset of 2 million samples, we did get 
equivalent results to Near Miss. However, the performance did not justify the processing time 
and cost.  

    Model Selection:  

We compare the performance of five classification models: K Nearest Neighbor, Logistic
 Regression, Random Forest, XGBoost and ​​HistGradientBoostingClassifier.

Hyper Parameter Selection

We completed a grid search for HistGradientBoostingClassifier.  We completed a randomized search for Random Forest and XGB to minimize processing time.  We completed separate parameter searches for undersampling and near miss datasets.  


    Cross Validation:

Data sets were split 67:33 for training and testing respectively.  Isolating a third of the dataset for testing exposes models that are overfit to training data. 


Results:

Model Performance:

Random Forest was the highest performing model
Logistic Regression was the lowest scoring model
Near Miss data preparation improved model performance by 12-20%
K Nearest Neighbor benefited the most from Near Miss 

![alt text](https://github.com/JOSHUAGITBERG/bitcoin_heist_ransomware/blob/main/images/F1-Scores-by-Model-Dataset.png)

Ransomware Label Identification:

![alt text](https://github.com/JOSHUAGITBERG/bitcoin_heist_ransomware/blob/main/images/F1-Scores-by-Label.png)





