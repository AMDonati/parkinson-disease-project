# Parkinson Disease Project - ideas of precise topics
## _Objective: Defining the precise topic on the week of July 16th_

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

## Idea #1. Building a recommender system suggesting the best treatment(s) for each PD subject
### AI & Healthcare topic: precision medicine
#### use cases:
* **For Doctors**: decision support tool for selecting the best treament for each of their patients
* **For Patients/Patients Families**: Improved quality of life due to a more "personalised" treatment
* **For Researchers looking for new PD treatments**: Tool that could give them a better understanding of the pros/cons & efficiency of each treatment, and their suitability for each PD's "subject type"

#### Data Science Challenges / Techniques: 
* Database building to gather all the subjects' information in one table
* Feature Engineering to select the relevant set of features to be used for the recommender system model
* Statistical techniques to select the features (correlation...)
* Machine Learning Techniques (Clustering, Classification), probably using gradient boosted trees and random forest classifier. 
* Recommender System Building

#### Reference documents: 
* Towards Healthcare (Aware) Recommender Systems:
http://www.christophtrattner.info/pubs/DH2017.pdf
* A Survey of Context-Aware Healthcare Recommender Systems:
https://trello-attachments.s3.amazonaws.com/5b3e6dbb7d721073e66fcdd6/5b3e8b577999c8ac8a382e7f/23c7ed10f9ca1e87732fd79516c3615a/ART20178861_Survey-of-HRS_VERY-INTERESTING_READ.pdf
* A recommender system for medical imaging: 
https://trello-attachments.s3.amazonaws.com/5b3e6dbb7d721073e66fcdd6/5b3e8c4f553d29404f05a65c/4fb175ab36fec2ed66a31fff2a960d9a/A-recommnder-system-for-medical-imaging_READ_authors-to-contact.pdf
* Recommender Systems for Health Informatics:State-of-the-Art and Future Perspectives:
https://trello-attachments.s3.amazonaws.com/5b3e6dbb7d721073e66fcdd6/5b3e8d000632774b9de392d7/3200d28b9ccf02e3ad06592c4cba21a4/RS-and-HealthInformatics_READ_a-relire.pdf

* Current and Experimental diseases in PD: 
https://trello-attachments.s3.amazonaws.com/5b3e6dbb7d721073e66fcdd6/5b3e8ac6660f353fa34d758d/889de8dccc375f020c4773081e774753/Current_%26_experimental_diseases_in_PD_REF.pdf
* Evaluation of treatments in PD, psychosis and other dementias: 
https://trello-attachments.s3.amazonaws.com/5b3e6dbb7d721073e66fcdd6/5b3e8b2a36c7535e743f1202/b21bf60979549d56d17bc4f2fbeb523c/Evaluation_of_treatments_in_dementia%2C_psychosis_for_PD_READ_ref.pdf


#### Additonal datasets that could be used: 
* 2 others clinical studies for PD subjects: 
  * https://www.coriell.org/Search?q=%22PARKINSON%20DISEASE%22&grid=1
  * https://www.biosend.org/pd_specimens.html
  
* UCI ML repository datasets: 
  * https://archive.ics.uci.edu/ml/datasets/Parkinson+Speech+Dataset+with++Multiple+Types+of+Sound+Recordings
  * https://archive.ics.uci.edu/ml/datasets/Parkinson+Disease+Spiral+Drawings+Using+Digitized+Graphics+Tablet
  
* Physiomed datasets - Keystrokes, Tremors and Gait:
  * https://physionet.org/physiobank/database/nqmitcsxpd/
  * https://physionet.org/physiobank/database/tremordb/
  * https://physionet.org/physiobank/database/gaitndd/
  * https://physionet.org/physiobank/database/gaitdb/
  * https://physionet.org/physiobank/database/gaitpdb/

#### Potential difficulties of this topic: 
-Doing correctly the feature engineering to select the right variables to use as an input of the recommender system
> Requires domaine expertise

## Idea #2. Building a prediction model for predicting the evolution of the disease for each subject 
### AI & Healthcare topic: diagnosis prediction/accuracy 
#### use cases: 
* FOR DOCTORS: Early detection of PD subjects, anticipation of their patients' disease evolution.
* FOR PD PATIENTS: 
  * For people with risk of getting PD: early detection and monitoring 
  * For early-stage/late-stage PD people: monitoring better their disease by knowing the expected evolution
  
#### Data Science Challenges / Techniques: 
* Database building to gather all the subjects' information in one table
* Feature Engineering to select the relevant set of features to be used as input for the prediction model
* Statistical techniques to select the features (correlation...)
* Machine Learning Techniques (Regression), probably using linear regression with L1/L2 regularization, random forest(regression version) and linear neural networks.  
* Data Visualisation Tools to present the results


#### Additonal datasets that could be used: 
* Same as topic #1 

#### Potential difficulties of this topic:
-Doing correctly the feature engineering to select the right variables to use as an input of the prediction model
> Requires domaine expertise
* Definition/Classification of the different stages of the disease (as prediction outputs) can be quite complicated


## Idea #3. Specific focus on brain scans analysis of PD subjects 
### AI & Healthcare topic: biomedical vision / CAD for neuroimaging  
#### use cases: 
* DOCTORS: Decision Support tool to analyze brain scans 
* RESEARCHERS: Support Tool to research new MRI techniques adaptated to PD Brain damages diagnosis

#### Data Science Challenges / Techniques: 
* Data pre-processing and database building from multiple datasets
* Advanced machine learning & deep learning techniques for brain scans analysis
  * Possibly: few-shot learning, transfer learning, ensembling neural networks 
  
#### Reference documents: 
* How Machine Learning is shaping cognitive neuroimaging: 
https://gigascience.biomedcentral.com/track/pdf/10.1186/2047-217X-3-28
* Medium Article: Deep Learning Techniques for MRI
https://medium.com/stanford-ai-for-healthcare/dont-just-scan-this-deep-learning-techniques-for-mri-52610e9b7a85
* Deep Learning in Medical Imaging: Overview and Future Promise of an Exciting New Technique
https://arxiv.org/pdf/1704.06825.pdf
* Deep Learning for Brain MRI Segmentation: State of the Art and Future Directions: 
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5537095/pdf/10278_2017_Article_9983.pdf

#### Additional datasets that could be used:
* NEUROVAULTS: resting state fMRIs of PD subjects: 
https://neurovault.org/collections/2953/

* NEUROCON Project: resting state fMRIs & T1-weighted scans
http://fcon_1000.projects.nitrc.org/indi/retro/parkinsons.html

#### Potential difficulties of this topic:
* Which baseline to compare the algorithm's performance to? 
* Analysis of the Brain MRIs requires a lot of domaine expertise...






