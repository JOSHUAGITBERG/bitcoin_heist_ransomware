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

<Insert Results Visual Here>

Data Description

<Describe data>

Data Preparation

<Describe steps to cleanse data and details about over sampling etc>







  


