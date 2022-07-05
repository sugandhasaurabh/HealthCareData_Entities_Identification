# HealthCareData_Entities_Identification
> ‘BeHealthy’, a health tech company, aims to connect the medical communities with millions of patients across the country.

‘BeHealthy’ has a web platform that allows doctors to list their services and manage patient interactions and provides services for patients such as booking interactions with doctors and ordering medicines online. Here, doctors can easily organise appointments, track past medical records and provide e-prescriptions. So, ‘BeHealthy’ are providing medical services, prescriptions and online consultations and generating huge data day by day. 




## Table of Contents
* [General Info](#general-information)
* [Business Goals](#business-goals)
* [Problem Statement](#problem-statement)
* [Expected Solution Steps](#expected-solution-steps)
* [Model Building](#model-building)
* [Dataset](#dataset)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)
* [Contact](#contact)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
‘BeHealthy’ has a web platform that allows doctors to list their services and manage patient interactions and provides services for patients such as booking interactions with doctors and ordering medicines online. Here, doctors can easily organise appointments, track past medical records and provide e-prescriptions. So, ‘BeHealthy’ are providing medical services, prescriptions and online consultations and generating huge data day by day.



## Business Goals
Let’s take a look at the following snippet of medical data that may be generated when a doctor is writing notes to his/her patient or as a review of a therapy that he or she has done.

“The patient was a 62-year-old man with squamous cell lung cancer, which was first successfully treated by a combination of radiation therapy and chemotherapy.”

As you can see in this text, a person with a non-medical background cannot understand the various medical terms. We have taken a simple sentence from a medical data set to understand the problem and where you can understand the terms ‘cancer’ and ‘chemotherapy’.


## Problem Statement
Suppose you have been given such a data set in which a lot of text is written related to the medical domain. As you can see in the dataset, there are a lot of diseases that can be mentioned in the entire dataset and their related treatments are also mentioned implicitly in the text, which you saw in the aforementioned example that the disease mentioned is cancer and its treatment can be identified as chemotherapy using the sentence.

But, note that it is not explicitly mentioned in the dataset about the diseases and their treatment, but somehow, you can build an algorithm to map the diseases and their respective treatment.



## Expected Solution Steps
1. You need to process and modify the data into sentence format. This step has to be done for the 'train_sent' and ‘train_label’ datasets and for test datasets as well.
2. After that, you need to define the features to build the CRF model.
3. Then, you need to apply these features in each sentence of the train and the test dataset to get the feature values.
4. Once the features are computed, you need to define the target variable and then build the CRF model.
5. Then, you need to perform the evaluation using a test data set.
6. After that, you need to create a dictionary in which diseases are keys and treatments are values.



## Model Building
1. Data preprocessing
2. Concept identification
3. Defining the features for CRF
4. Getting the features words and sentences
5. Defining input and target variables
6. Building the model
7. Evaluating the model
8. Identifying the diseases and predicted treatment using a custom NER



## Dataset
The dataset is available under "Data Files" folder. There are 4 datasets provided under this folder.
1. train_sent
2. test_sent
3. train_label
4. test_label

You have the train and the test datasets; the train dataset is used to train the CRF model, and the test dataset is used to evaluate the built model.

First, you will understand the ‘train_sent’ and the ‘test_sent’ datasets. Here, you need to understand that each word in this dataset is provided in a single line. So, first, you need to club all these words together to form the sentences. Moreover, there are blank lines given in the dataset that have been highlighted in the image given above. These blank lines indicate that a new sentence is starting from the next line onwards to the next blank line.

Now, let’s take a look at the next datasets that are named ‘train_label’ and ‘test_label’. The above dataset is about the labels corresponding to the diseases and the treatment. There are three labels that have been used in this dataset: O, D and T, which are corresponding to ‘Other’, ‘Disease’ and ‘Treatment’, respectively.

These labels correspond to each word that is available in the ‘train_sent’ and 'test_sent' datasets. So, there is one-to-one mapping of each label available in the 'train_label' and 'test_label' datasets with the words that are available in the 'train_sent' and 'test_sent' datasets, respectively. You need to again create the lines of labels corresponding to each sentence in the ‘train_sent’ and the ‘test_sent’



## Conclusions
- The entire model is based on semantic processing.
- Top 25 NOUN or PROPN PoS (Part Of Speech) tags are:
[('patients', 492),
 ('treatment', 281),
 ('%', 247),
 ('cancer', 200),
 ('therapy', 175),
 ('study', 154),
 ('disease', 142),
 ('cell', 140),
 ('lung', 116),
 ('group', 94),
 ('chemotherapy', 88),
 ('gene', 87),
 ('effects', 85),
 ('results', 78),
 ('women', 77),
 ('use', 73),
 ('risk', 71),
 ('cases', 71),
 ('surgery', 71),
 ('analysis', 70),
 ('rate', 67),
 ('response', 66),
 ('survival', 65),
 ('children', 64),
 ('effect', 63)]

 - A dictionary is created with keys as diseases name and values as Treatment
 - The treatment for 'hereditary retinoblastoma', from dictionary, is found to be "radiotherapy"



## Technologies Used
- pycrf
- sklearn-crfsuite
- spacy
- nltk



## Acknowledgements
Sugandha Saurabh | github - @sugandhasaurabh


## Contact
Created by Sugandha Saurabh | github - @sugandhasaurabh


