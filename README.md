# capstone_heart_disease
## Currently in ramping-up branch
   This file describes the contents of the heart-disease directory.

   This directory contains 1 database concerning heart disease diagnosis.
   All attributes are numeric-valued.  The data was collected from the
   following location:

     1. Cleveland Clinic Foundation (cleveland.data)

   **Digital Citizens**
   
   **August 09, 2019**


1. **Title**: Heart Disease Databases

2. **Source Information**:
   (a) Creators: 
       1. V.A. Medical Center, Long Beach and Cleveland Clinic Foundation:
             Robert Detrano, M.D., Ph.D.

3. **Relevant Information**:
     This database contains 76 attributes, but all published experiments
     refer to using a subset of 14 of them.  In particular, the Cleveland
     database is the only one that has been used by ML researchers to 
     this date. The "goal" field refers to the presence of heart disease
     in the patient.  It is integer valued from 0 (no presence) to 4.
     Experiments with the Cleveland database have concentrated on simply
     attempting to distinguish presence (values 1,2,3,4) from absence (value
     0).  
   
     The names and social security numbers of the patients were recently 
     removed from the database, replaced with dummy values.

     One file has been "processed", that one containing the Cleveland 
     database.
4. **Number of Instances:** 
        Database:    # of instances:
          Cleveland: 303

5. **Number of Attributes: 76 (including the predicted attribute)**

6. **Features Information:**
    It's a clean, easy to understand set of data. However, the meaning of some of the column headers are not obvious. Here's what they mean,

 - **age**: The person's age in years
 - **sex**: The person's sex (1 = male, 0 = female)
 - **cp:** The chest pain experienced (Value 1: typical angina, Value 2: atypical angina, Value 3: non-anginal pain, Value 4: asymptomatic)
 - **trestbps:** The person's resting blood pressure (mm Hg on admission to the hospital)
 - **chol:** The person's cholesterol measurement in mg/dl
 - **fbs:** The person's fasting blood pressur (> 120 mg/dl, 1 = true; 0 = false) 
 - **restecg:** Resting electrocardiographic measurement (0 = normal, 1 = having ST-T wave abnormality, 2 = showing probable or definite left ventricular hypertrophy by Estes' criteria)
 - **thalach:** The person's maximum heart rate achieved
 - **exang:** Exercise induced angina (1 = yes; 0 = no)
 - **oldpeak:** ST depression induced by exercise relative to rest ('ST' relates to positions on the ECG plot. See more [here](https://litfl.com/st-segment-ecg-library/))
 - **slope:** the slope of the peak exercise ST segment (Value 1: upsloping, Value 2: flat, Value 3: downsloping)
 - **ca:** The number of major vessels (0-3)
 - **thal:** A blood disorder called thalassemia (3 = normal; 6 = fixed defect; 7 = reversable defect)
 - **target:** Heart disease (0 = no, 1 = yes)

To avoid [HARKing](https://journals.sagepub.com/doi/abs/10.1207/s15327957pspr0203_4) (or Hypothesizing After the Results are Known) I'm going to take a look at online guides on how heart disease is diagnosed, and look up some of the terms above.

**Diagnosis**: The diagnosis of heart disease is done on a combination of clinical signs and test results. The types of tests run will be chosen on the basis of what the physician thinks is going on [1](https://www.mayoclinic.org/diseases-conditions/heart-disease/diagnosis-treatment/drc-20353124), ranging from electrocardiograms and cardiac computerized tomography (CT) scans, to blood tests and exercise stress tests [2](https://www.heartfoundation.org.au/your-heart/living-with-heart-disease/medical-tests).

Looking at information of heart disease risk factors led me to the following: **high cholesterol, high blood pressure, diabetes, weight, family history, air pollution, and smoking** [3](https://www.bhf.org.uk/informationsupport/risk-factors). According to another source [4](https://www.heart.org/en/health-topics/heart-attack/understand-your-risks-to-prevent-a-heart-attack), the major factors that can't be changed are: **increasing age, male gender and heredity**. Note that **thalassemia**, one of the variables in this dataset, is heredity. Major factors that can be modified are: **Smoking, high cholesterol, high blood pressure, physical inactivity, and being overweight and having diabetes**. Other factors include **stress, alcohol and poor diet/nutrition**.

I can see no reference to the 'number of major vessels', but given that the definition of heart disease is **"...what happens when your heart's blood supply is blocked or interrupted by a build-up of fatty substances in the coronary arteries"**, it seems logical the *more* major vessels is a good thing, and therefore will reduce the probability of heart disease.

Given the above, I would hypothesis that, if the model has some predictive ability, we'll see these factors standing out as the most important.

7. **Missing Attribute Values**: Distinguished with value -9.0. (Have to be treated)

8. **Class Distribution**:
        Database:      0   1   2   3   4 Total
          Cleveland: 164  55  36  35  13   303
          
