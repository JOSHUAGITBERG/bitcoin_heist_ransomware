Background:

Ransomware Facts:

   Ransomware is a cyber attack vector that started demanding payment in bitcoin starting around 2013 with the emergence of “CryptoLocker”. Ransomware attacks have since become more common.  According to service provider AAG:
Ransomware attacks cost the US healthcare sector an estimated $7.8 billion in downtime alone in 2021
There were over 200 million ransomware attacks across the globe in the first half of 2022   
Ransomware accounted for around 20% of cyber breaches in 2022 

Bitcoin:

  Bitcoin is a cryptocurrency that allows direct exchange between digital addresses recorded on a blockchain.  Ransomware uses bitcoin to extract ransom because transactions are unregulated, digital, fast, global, irreversible, and anonymous.  However, because bitcoin has a publicly viewable ledger, we can analyze transactions to look for patterns that may indicate whether a given address or transaction maybe part of a ransomware network.  The following study analyzes a dataset drawn from the bitcoin blockchain to attempt to predict whether a given address may be a ransomware address.  The ability to identify known bad addresses would help authorities track down organizations perpetrating ransomware attacks, and could be used in real time by exchanges to flag suspicious activity within their network.  

Summary Findings:

   We were able to build a random forest model that can identify a ransomware address with over 90% accuracy. 


Approach:

  We built models with three different classifiers, including Knearest Neighbor, Logistic Regression, and RandomForest.  We also treated the data with three different approaches, undersampling, smote, and nearest neighbor.  After modeling and comparing the results against a test data set for each approach, we found that SMOTE resampling combined with Random Forest provided the highest F-scores.  

Insert Results Visual Here…

Data Description…

Describe data…

Data Preparation…

Describe steps to cleanse data and details about over sampling etc



Work in Progress:  Workbook is complete but I have not completed an analysis.  I will write this up after I have summary findings to present. 

General Structure:

Introduction-  a little about bitcoin and ransomware.  Describe Business Problem and how this model can address it in a real world situation.  

Summary Results-  Describe findings around specific features.  Example… long length indicates ransomware (or whatever… still in progress)

Data-  Summarize the Kaggle data information and structure.  

Data Preparation-  Discuss Smote, Near Miss and Manual Approaches.

Data Signal-  Discuss relative performance of Smote and Near Miss.

Raw Results:

Under KNN Pscore:  			0.722957629465522
Smote KNN Pscore:  			0.9002395691253104
Near Miss KNN Pscore:  		0.8335715213719631

Under logistic regression Pscore:  	0.5761379971250599
Smote logistic regression Pscore:  	0.6288116628464037
Near Miss logistic regression Pscore:  	0.6876893726854449

Under RandomForest Pscore:  	0.7742226228030644
Smote RandomForest Pscore:  	0.958953306708514
Near Miss RandomForest Pscore:  	0.8614995338926621




  

