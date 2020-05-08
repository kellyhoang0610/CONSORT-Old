# CONSORT-Classification
Developing an automatic classification system to classify  CONSORT checklist items reported in clinical trial publications. 

1. Data Preprocessing:
- CONSORT_Manual_Annotated_Data_Preprocessing.ipynb: read XML articles from /efs/CONSORT/skr-consort/datasets/XML_50/ and map sentences with the manual annotation.
- CONSORT_Heuristic_Annotated_Data_Preprocessing.ipynb: rean XML articles from /efs/CONSORT/HeuristicsBasedAnnotations/all_agree_consort_two_strict_editedfor6b_11b to get automatic annotated data
2. Classifier development:
- CONSORT_Classifier_GridSearchCV_ManualDataOnly.ipynb: classifier that use manual annotated data only.
  + Using ony manual annotated data for both training & testing.
  + Features: n-grams of sentence text, section header, metamap concepts, metamap semantic types. 
  + ML method: SVM using GridSearch sklearn. 
- CONSORT_Classifier_GridSearchCV_ValidationSet-MetaMap.ipynb: classifier that use both manual and automatic annotated data:
  + Using automatic annotated data for training and manual annotated data for validation & testing (validation is used for fine tuning model)
  + Features: n-grams of sentence text, section header, metamap concepts, metamap semantic types. 
  + ML method: SVM using GridSearch sklearn. 
