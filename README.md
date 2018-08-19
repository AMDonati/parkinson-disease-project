# Parkinson Disease Project - DSR
## Subject: Modelling Parkinson Disease Progression and predicting best treatment strategies for PD patients with Machine Learning/Deep Learning 
## AI & Healthcare topics: diagnosis prediction/accuracy, precision medecine with personalized treatments

### 0. Project context
* **number of hours to work on it**: ~350-400h 
* **Project output**: 
 * Github repo with reproducible code
 * Oral Presentation (~10/15min + questions) in front of panel of companies and data scientists in Berlin 
 * Slides Deck
 * _Optional_: Video about the Project Process, Medium Article, Scientific paper (if relevant and possible)
 
### 1. Abstract / Project objectives:
The main goal of this project is predicting Parkinson Disease (PD) Progression over time for a set of patients from a clinical study.

More precisely, the project objectives are:
Starting from a dataset of Electronic Health Records of patients with 4 different clinical diagnosis (PD diagnosed patients, 400 de novo PD subjects - newly diagnosed and unmedicated, SWEDD and healthy control subjects),I will:
* **Classify clinical diagnosis for each patient**
* **Predict Parkinson Disease Progression over time** using:  
   * 2a. First, only biological biomarkers . 
   * 2b. Add in a second time MRI data (raw brain scans from the PPMI dataset) . 
 (the idea is to compare the performance of the models with and without MRI data, as performing MRI is expensive for hospitals and also not easy to process as data).
* **Predict best treatment strategy associated to each patient and each future disease state**
* If enough time: **_predicting patients' time of death_** (see recent article about Google having done such predictions)
* If enough time: **_ANALYZE TEMPORAL PATTERNS OF BIOMARKERS USING LONGITUDINAL STABILITY SELECTION_**
(as done on AD in Fused Sparse Group Lasso Paper)

_NB: SWEDD= Scans without evidence of dopamine deficit: patients who look like they have PD in terms of symptom but subsequent functional imaging assessment does not confirm this._
source: http://www.acnr.co.uk/SO10/ACNRSO10_30_SWEDD_article.pdf


### 2. **MAIN DATASET**: 
http://www.ppmi-info.org/access-data-specimens/download-data/
* Data Summary
![Data Summary](https://github.com/AMDonati/parkinson-disease-project/blob/master/assets%20/PPMI-intro-info.png)
* Data Pop
![Data pop](https://github.com/AMDonati/parkinson-disease-project/blob/master/assets%20/PPMI-pop-info.png)
* Patients Hospital visits timeline (timeseries period): 
![Patients hospital visits timeline (timeseries period](https://github.com/AMDonati/parkinson-disease-project/blob/master/assets%20/PPMI-visits-timeline.png)
* Schedule of activities for the clinical studies here: (http://www.ppmi-info.org/wp-content/uploads/2018/02/PPMI-AM-13-Protocol_SCHEDULE-OF-ACTIVITIES-1.pdf)

* data dictionnary annotated here: https://docs.google.com/spreadsheets/d/1Q-0zAG_oBfuo21s5xzN6Vwck5NT0GyP0K3KxiWpxO58/edit#gid=782043355 (work in progress)

* Complete dataset can be downloaded here: https://github.com/AMDonati/parkinson-disease-project/blob/master/data/PPMI-final-dataset-382018.zip
* additionnal dataset info: https://www.ppmi-info.org/study-design/research-documents-and-sops/

### 3. DS main challenges for this project: 
* Multi-modal (dataframes + MRI scans) multi-label classification problem of timeseries with features selection depending on the label prediction (the PD predominant biomarkers are depending on the disease state)


### 4. Use cases: 
* **FOR DOCTORS**: 
   * Early detection of PD subjects
   * Improving disease accuracy, 
   * Anticipation of their patients' disease evolution
   * support to decision for choosing treatments for patients
* **FOR PD PATIENTS**: 
  * For people with risk of getting PD: early detection and monitoring 
  * For early-stage/late-stage PD people: monitoring better their disease by knowing the expected evolution
  * Finding the best treatment that will improve the quality of life of PD people
* **FOR HOSPITALS**: 
 * cost reductions by improved patient management & treatment optimization
 * operations improvement by predicting patients future visits, med supplies, etc...
  
### 5.DS Process for the project 
1. **Data Processing/Cleaning**: Merge/Join of Tables (eventually using PyTables)

2. **EDA**: 
* timeseries analysis & plotting
> look @ sparsity, irregularity,trends... 

3.**Feature Engineering:** (if classic ML is used)
  * Manual Feature Engineering with the help of doctors 
  * Statistical techniques to find correlation between features
  * Classic Feature Engineering Techniques for ML -> use manifold learning:
   * PCA: http://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html
   * t-SNE: https://lvdmaaten.github.io/tsne/
   https://bl.ocks.org/Fil/b07d09162377827f1b3e266c43de6d2a
   * isomap: 
 http://scikit-learn.org/stable/modules/manifold.html . 
 https://github.com/cc-skuehn/Manifold_Learning . 
 https://towardsdatascience.com/reducing-dimensionality-from-dimensionality-reduction-techniques-f658aec24dfe
   * autoencoders
  
4. **ML/DL models to try:** 
 * Baseline: a statistical model > the one for a multivariate timeseries with endogeneous variables without trends and without seasonality = VARMA. 
     * other possibilities: discounted median, persistence model. 
 > Some references: https://machinelearningmastery.com/persistence-time-series-forecasting-with-python/
 
 * "Explainable" models: gradient-boosted trees, Random Forest
> Issue of large numbers of features for these models though...

 * DL Models to be modified to include incertainty with bayesian models
    * Hidden Markov Models
    > About HMMs for disease progression: https://web.engr.oregonstate.edu/~lif/nips2015_CTHMM_learning_camera_ready.pdf
    > About HMMs for TS classification: https://towardsdatascience.com/hidden-markov-models-for-time-series-classification-basic-overview-a59b74e5e65b
    * LSTM, GRU
    * Seq2seq, 1D-CNN?
 _reference paper for timeseries foreacast of EHR_: https://arxiv.org/pdf/1706.03446.pdf (to print)
    
About chossing between HMM & RNNs: 
* https://www.quora.com/When-would-one-use-a-Hidden-Markov-Model-instead-of-a-Recurrent-Neural-Network
* https://stats.stackexchange.com/questions/20429/what-are-the-differences-between-hidden-markov-models-and-neural-networks
* https://pub.uni-bielefeld.de/download/2903474/2907910
  
  > **NB: maybe the problem of allocating treatments to disease states over time could be solved by reinforcement learning as well...** See these links:
  * [Google scholar search for RL for adaptative treatments strategies] (https://scholar.google.com/scholar?oi=gsb95&q=reinforcement%20learning%20for%20medical%20treatments%20decisions&lookup=0&hl=en)
  * [An experimental design for the development of adaptive treatment strategies] (https://deepblue.lib.umich.edu/bitstream/handle/2027.42/39201/2022_ftp.pdf?sequence=1&isAllowed=y)
  * [Informing sequential clinical decision-making through reinforcement learning: an empirical study] (https://link.springer.com/content/pdf/10.1007/s10994-010-5229-0.pdf)
  * [Customizing Treatment to the Patient: Adaptive Treatment Strategies] (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1924645/)
  
 * see also this article from MIT news using RL for reducing drug doses: http://news.mit.edu/2018/artificial-intelligence-model-learns-patient-data-cancer-treatment-less-toxic-0810
  
  
6. **Outputs of the model** . 
For each patient: 
* a vector of disease states for different timestamps (multiple labels for each timestamp corresponding to UPDRS scale) . 
> link to UPDRS scale: UPDRS: http://www.etas.ee/wp-content/uploads/2013/10/updrs.pdf
* The associated treatment strategy related to the disease state (multiple labels as well)
* The estimated time of death 

7. **Data Visualisation to present the results** . 
Plots comparating the performance of the different models for different metrics

### 4. DS tools to be used (Python Libraries...): 

| **DS Process**           | Tool/Python lib                                                  | Comments                  |
| ----------------         |:-------------:                                                   | -----:                    |
| 0. Project Management    | Trello, slack, Github                                                                        |
| 1. Data Processing       | PyTables? or only pandas                                         |Mosty done                 |
| 2. EDA                   | Cufflinks/plotly, Seaborn, Scipy, statsmodels.tsa                |Mostly done                |
| 3. Feature Engineering   | sci-kit learn                                                    |Manually done for now .    |
| 4a. Classic ML           | sci-kit learn                                                    |                           |
| 4b. DL                   | keras with TensorFlow BE, Tensorboard, Google Open Cloud/AWS     |tutos started              |
| 5. Dataviz               | TBD, probably Seaborn                                            |                           |

#### Links: 
* http://www.statsmodels.org/stable/tsa.html
* for quick dataviz on dataframes: use cufflinks: https://plot.ly/ipython-notebooks/cufflinks/
* For DL: 
  * [NN Playground] (https://playground.tensorflow.org/#activation=tanh&batchSize=30&dataset=spiral&regDataset=reg-plane&learningRate=0.3&regularizationRate=0&noise=0&networkShape=4,2&seed=0.51575&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false)
  * [Tensorboard](https://www.tensorflow.org/guide/summaries_and_tensorboard)
  * GPUs: Google Open Cloud (Free), AWS
  
#### Python tricks to used
* Pickles
> https://docs.python.org/2/library/pickle.html . 
> https://pythontips.com/2013/08/02/what-is-pickle-in-python/

### 8. Potential Challenges araised by the subject
* For classic ML techniques: Doing correctly the feature engineering to select the right variables to use as an input of the prediction model

### 9. List of contacts that could help me & summary of discussions (other than mentor(s))
see here: https://github.com/AMDonati/parkinson-disease-project/wiki/useful-contacts-&-discussions-summary

 ### 10. Reference Documents
 * see list here: https://github.com/AMDonati/parkinson-disease-project/wiki/reference-documents
 * See papers summary here: https://docs.google.com/spreadsheets/d/1TEL4umtQPdPPhzf092iMQgvmi9pID5UMrCdndo6ZJsE/edit#gid=0
  
 
 ### 11. Additonal datasets that could be used: 
See here: https://github.com/AMDonati/parkinson-disease-project/wiki/Other-PD-medical-datasets
 
 ---------------
 
 ### Parkinson News to check: 
 https://parkinsonsnewstoday.com/2018/07/31/ema-endorses-use-of-imaging-radioactive-tracer-to-improve-parkinsons-clinical-trial-recruitment/







