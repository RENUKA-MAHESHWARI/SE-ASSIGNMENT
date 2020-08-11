# A Machine Learning Approach for Vulnerability Curation


 #### Authors  : Chen Yang, Andrew Santosa, Ang Ming Yi, Abhishek Sharma , Asankhaya Sharma, David Lo


>Venue Tue 30 Jun 2020 14:00 - 14:12 at MSR:Zoom - ML4SE 
>> Chair(s): Kevin Moran

[PAPER LINK]( https://2020.msrconf.org/details/msr-2020-papers/22/A-Machine-Learning-Approach-for-Vulnerability-Curation)

#### Media
https://youtu.be/hZcxtgwNvIE

INTRODUCTION AND MOTIVATION :

   This paper is on machine learning system and vulnerability issues and its curation.

Software compositioin analysis reports the vulnerabilities in the open source libraries because most of the software applications 
use open-source libraries.

Software Compositon Analysis is a system that is used to scan the applications to report the vulnerable libraries.

Security researchers curate database by the help of various sources. There are many open-source libraries that are not identified by 

national  vulnerability database.

Some sources that are used for curation are :

National Vulnerability Database(NVD),JIRA tickets,Bugzilla issues,Github issues,ithub pullrequests,Git commits,Mailing lists,Vendor Release 
Notes.
Therefore curation is manual.There is about over 2.6 million open-source libraries and more than 50k github repositries and many more.

To solve these vulnerability issues they introduced 'MACHINE LEARNING SYSTEM'.

Machine learning system is used to to check either the input data is vulnerability related or not.

Previously the approach for the curation of vulnerability used manually labled data from curated datbase to train new models and because of 

this large amount of data is wasted.

Therefore to utilize the unused data the machine llearning system perform semi-supervised learning or self training in which production 

models are reapplied to the unlablled data through which increase the amount of labelled data to train new models.And it maximise the 

improvement of the models quality at each iteration of pipeline.

There are two data sources that are textual data source and code source.
Word2vec vectors present on th text present in the data we collect.

Self training works as a threshold (t) is used for models to check/predict either it is vulnerability related or not related.

If the prediction score is greater than threshold the data is said to be vulnerability related and if the prediction score is less than 

threshold data is said to be vulnerability un-related.

As new models deployed thresholds are also updated.



EXPERIMENTS :

     
    1. MODEL VALIDATION :

Stability Validation:  Stability metrics were used to measure the the model deployments vulnerabilities changed to non-vulnerability.
Test is perfomed on half of lablled data having same positive and negative labels.

                
              deployment stability=  (|〖TP〗_n∩〖TP〗_p |+|〖TN〗_n∩〖TN〗_p | )/(test dataset size)

Where n refers new model and p refers production model.

Performance Validation:  For validation precision and recall metrics were collected that are :


   Precision=  (|TP|)/(|TP|+|FP|)

   Recall=  (|TP|)/(|TP|+|FN|)

Where TP represents true positive, FP refers false positive and FN refers false negative.


Precision is the ratio between true positives and all predicted positives. High precision removes false positives.

Recall is used to indicate the true vulnerability related items.Higher the recall more vulnerability related item.


   2.  MODEL DEPLOYMENT : 

Human lablled data is used to train production Model.
Self training is applied to train new models against production model.


LIMITATIONS : 

-  Limitation to textual data
-  Weakness to data imbalance
-  Ignorance of label change


RESULTS : 

- Machine learning system is introduced to provide pipeline from data collection, model production and its training to validate new models.
- Self training is used to utilize unlabelled data.
- To solve the problems of production machine learning deployment use of deployment stability metric should be helpfull.
- Standard precision recall metrics were used to evaluate model performance.
