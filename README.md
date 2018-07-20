# Parkinson Disease Project - DSR
## Subject: A Probabilistic Model to predict the future states of the disease progress of Parkinson Disease among a population of patients
## AI & Healthcare topic: diagnosis prediction/accuracy


### **MAIN DATASET**: http://www.ppmi-info.org/access-data-specimens/download-data/
#### study pop:
* 400 de novo PD subjects - newly diagnosed & unmedicamented
* 200 age and gender matched healthy controls
* ~70-80 SWEDD subjects
> Subjects followed for a min of 3 years, and a max of 5 years.

#### Clinical data collection: 
* Motor Assessments
* Neuropsychiatric/neurobehavioral testing
* Olfaction
* DatScan Imaging, MRI

_TO COMPLETE_

### Use cases: 
* **FOR DOCTORS**: Early detection of PD subjects, Improving disease accuracy, anticipation of their patients' disease evolution 
* **FOR PD PATIENTS**: 
  * For people with risk of getting PD: early detection and monitoring 
  * For early-stage/late-stage PD people: monitoring better their disease by knowing the expected evolution
  
#### Data Science Techniques to be used: 
1. **Data Processing/Cleaning**: Merge/Join of Tables (eventually using PyTables), filling missing values

2.**Feature Engineering:**
  * Manual Feature Engineering with the help of doctors 
  * Statistical techniques to find correlation between features
  * Classic Feature Engineering Techniques 
  
3. **ML/DL models to try:** 
 * "Explainable" models: gradient-boosted trees, Random Forest
> Issue of large numbers of features for these models though...

 * DL Models to be modified to include incertainty with bayesian models (_litterature on the subject to be read_)
  * Hidden Markov Models
  * RNN
  * LSTM
  ...
  
4. **Outputs of the model**
For each patient subject: a vector of tuples (PD state (categorical variable), probability) for each period of time considered
> Think more in depth about the relevant output (talk with the doctors)

5. **Interactive DataViz Tools to present the results**
> Check all the tools available and select the best one. 

#### Potential Challenges of this topic:
* Doing correctly the feature engineering to select the right variables to use as an input of the prediction model
* Definition/Classification of the different stages of the disease (as prediction outputs) can be quite complicated

#### List of contacts that could help me: 
_TO COMPLETE_


#### Additonal datasets that could be used (if enough time):
* **2 others clinical studies for PD subjects:** 
  * https://www.coriell.org/Search?q=%22PARKINSON%20DISEASE%22&grid=1
  * https://www.biosend.org/pd_specimens.html
  
* **UCI ML repository datasets on PD:**
  * https://archive.ics.uci.edu/ml/datasets/Parkinson+Speech+Dataset+with++Multiple+Types+of+Sound+Recordings
  * https://archive.ics.uci.edu/ml/datasets/Parkinson+Disease+Spiral+Drawings+Using+Digitized+Graphics+Tablet
  
* **Physiomed datasets - Keystrokes, Tremors and Gait:**
  * https://physionet.org/physiobank/database/nqmitcsxpd/
  * https://physionet.org/physiobank/database/tremordb/
  * https://physionet.org/physiobank/database/gaitndd/
  * https://physionet.org/physiobank/database/gaitdb/
  * https://physionet.org/physiobank/database/gaitpdb/







