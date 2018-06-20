# 05_DSR_Portfolio_Project

# Elevator Pitch

## 1.DATA

### 1. sources
4 datasets from [the UCI ML repository](https://archive.ics.uci.edu/ml/datasets.html):  

_All these datasets are medical data related to Parkinson Disease, with a set of healthy patients (H) and patients with the Parkinson Disease(PD)_

#### __1. Dataset 1__
[Parkinson dataset](https://archive.ics.uci.edu/ml/datasets/parkinsons)  

**Features:**
![alt text](https://github.com/AMDonati/05_DSR_Portfolio_Project/blob/master/Parkinsons-dataset.png)

__**Short Description:**__
**Biomedical voice measurements of 31 voice recordings, including 23 with PD.**

__Attribute Information__:  
Matrix column entries (attributes):
* name - ASCII subject name and recording number
* MDVP:Fo(Hz) - Average vocal fundamental frequency
* MDVP:Fhi(Hz) - Maximum vocal fundamental frequency
* MDVP:Flo(Hz) - Minimum vocal fundamental frequency
* MDVP:Jitter(%),MDVP:Jitter(Abs),MDVP:RAP,MDVP:PPQ,Jitter:DDP - Several
* measures of variation in fundamental frequency
* MDVP:Shimmer,MDVP:Shimmer(dB),Shimmer:APQ3,Shimmer:APQ5,MDVP:APQ,Shimmer:DDA - Several measures of variation in amplitude
* NHR,HNR - Two measures of ratio of noise to tonal components in the voice
* status - Health status of the subject (one) - Parkinson's, (zero) - healthy
* RPDE,D2 - Two nonlinear dynamical complexity measures
* DFA - Signal fractal scaling exponent
* spread1,spread2,PPE - Three nonlinear measures of fundamental frequency variation

**Data usage**
Classification of PD vs Healthy

**Dataset Type:**  
.txt


#### __2. Dataset 2__
[Parkinson Telemonitoring dataset](https://archive.ics.uci.edu/ml/datasets/Parkinsons+Telemonitoring)  

**Features:**  
![alt text](https://github.com/AMDonati/05_DSR_Portfolio_Project/blob/master/Parkinsons-Telemonitoring.png)

__**Short Description:**__
**Biomedical voice measurements of 42 people with PD at home through Telemonitoring.**

__ATTRIBUTE INFORMATION__:  
* subject# - Integer that uniquely identifies each subject
* age - Subject age
* sex - Subject gender '0' - male, '1' - female
* test_time - Time since recruitment into the trial. The integer part is the
* number of days since recruitment.
* motor_UPDRS - Clinician's motor UPDRS score, linearly interpolated
* total_UPDRS - Clinician's total UPDRS score, linearly interpolated
* Jitter(%),Jitter(Abs),Jitter:RAP,Jitter:PPQ5,Jitter:DDP - Several measures of
* variation in fundamental frequency
* Shimmer,Shimmer(dB),Shimmer:APQ3,Shimmer:APQ5,Shimmer:APQ11,Shimmer:DDA -
* Several measures of variation in amplitude
* NHR,HNR - Two measures of ratio of noise to tonal components in the voice
* RPDE - A nonlinear dynamical complexity measure
* DFA - Signal fractal scaling exponent
* PPE - A nonlinear measure of fundamental frequency variation

**Data usage**  
Prediction of the Parkinson disease stage

**Dataset Type:**   
.txt


#### __3. Dataset 3__
[Parkinson Speech Dataset with Multiple Types of Sound Recordings dataset](https://archive.ics.uci.edu/ml/datasets/Parkinson+Speech+Dataset+with++Multiple+Types+of+Sound+Recordings)  

**Features:**
![alt text](https://github.com/AMDonati/05_DSR_Portfolio_Project/blob/master/Parkinsons-speech-w-multiple-sound-recordings.png)

__**Short Description:**__ 
**Recording of 26 different sounds recording for 40 subjects (20 PD, 20H):**
* sustained vowels  
* sustained words  
* sustained numbers
* short sentences


__Attribute Information__:

**Training Data File**:
column 1: Subject id

* colum 2-27: features
* features 1-5: Jitter (local),Jitter (local, absolute),Jitter (rap),Jitter (ppq5),Jitter (ddp),
* features 6-11: Shimmer (local),Shimmer (local, dB),Shimmer (apq3),Shimmer (apq5), Shimmer (apq11),Shimmer (dda),
* features 12-14: AC,NTH,HTN,
* features 15-19: Median pitch,Mean pitch,Standard deviation,Minimum pitch,Maximum pitch,
* features 20-23: Number of pulses,Number of periods,Mean period,Standard deviation of period, features 24-26: Fraction of locally unvoiced frames,Number of voice breaks,Degree of voice breaks

* column 28: UPDRS
* column 29: class information

**Test Data File**:
column 1: Subject id

colum 2-27: features
* features 1-5: Jitter (local),Jitter (local, absolute),Jitter (rap),Jitter (ppq5),Jitter (ddp),
* features 6-11: Shimmer (local),Shimmer (local, dB),Shimmer (apq3),Shimmer (apq5), Shimmer (apq11),Shimmer (dda),
* features 12-14: AC,NTH,HTN,
* features 15-19: Median pitch,Mean pitch,Standard deviation,Minimum pitch,Maximum pitch,
* features 20-23: Number of pulses,Number of periods,Mean period,Standard deviation of period,
* features 24-26: Fraction of locally unvoiced frames,Number of voice breaks,Degree of voice breaks

* column 28: class information

**Dataset Type:**  
.txt


#### __4. Dataset 4__
[Parkinson Disease Spiral Drawings Using Digitized Graphics Tablet](https://archive.ics.uci.edu/ml/datasets/Parkinson+Disease+Spiral+Drawings+Using+Digitized+Graphics+Tablet#)  

__**Short Description:**__ 
The PD and control handwriting database consists of 62 PWP (People with parkinson) and 15 healthy individuals.    From all subjects, three types of handwriting recordings (Static Spiral Test (SST), Dynamic Spiral Test (DST) and Stability Test on Certain Point (STCP)) are taken.  
Also the drawings of spirals belongs to the PWP are included in the dataset as image. Therefore, this dataset can also be used for regression.


**Data usage**
* Classification
* (Regression)

**Features:**
![alt text](https://github.com/AMDonati/05_DSR_Portfolio_Project/blob/master/Parkinsons-disease-spiral-drawings.png)

**Dataset Type:**  
.txt
.jpg

## 2. PROBLEM AND SOLUTION
