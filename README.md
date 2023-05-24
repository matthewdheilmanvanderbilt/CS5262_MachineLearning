[About](#about-the-project)  
[Data](#data)  
[Models](#models)  
[Timeline](#timeline)  
[Repo Structure](#repo-structure)  
[Getting Started](#getting-started)  
[Resources](#resources)  
[Contact](#contact-info)

# About The Project

## Goal
This project will attempt to predict if a person has a risk of a stroke based on information available about the person, such as age, gender, and comorbidities. Strokes are preventable and the monetary cost to prevent a stroke pale in comparison to the treatment cost after a person suffers a stroke. If all strokes could be eliminated in the US, there is a potential savings of $56 billion per year.

Stoke is the leading cause of death in the United States (1). It is the second largest cause of death worldwide (2). Strokes are a major cause of serious disability for adults (1). Every year, more than 795,000 people have strokes in the US (3). Stokes related costs in the US were nearly $56.6 billion between 2018 and 2019 (3). The US has the highest average cost per patient for stroke treatment of $59,900 (5). The CDC estimates 80% of stokes are preventable (4). High blood pressure is the single most important treatable factor (4). Other factors include life-style changes and medicine (6).



## Background
This project will be used to fulfill the first set of assignments for the Vanderbilt CS5265-50 (Foundations of Machine Learning) class. The project consists of delivering a machine learning application. The building of the project will be done over the course of six (6) weeks.
The purpose of the project is to:
1.	Setup the environment for the machine learning assignment
2.	Learn how to setup and use Google Colab
3.	Apply literate coding techniques in solving an analytical problem
4.	Learn to use pandas to solve a data exploration problem


The author of this project is Matt Heilman. The professor is Dana Zheng. The professor has asked the author to select a dataset will meet the following guidelines:
    *	Tabular/structured/2D (i.e., rows and columns)
    *	≥ 5000 samples/records/rows, but no more than 50k rows
    *	≥ 7 features/variables/columns, but no more than 25 columns
    *	Independence between data points (rows in your data)
    *	Identify a dataset that you can use for a binary classification task directly or after transformation
    *	Diverse data types for your columns:
    *	Continuous variables (e.g., measurements such as weight, temperature, etc.)
    *	Count variables (e.g., age, number of people in a classroom, etc.)
    *	Categorical variables (e.g., gender, type of Operating Systems, degrees of severity, etc.)


# Data
The data was sourced from the Stroke Prediction Dataset available at [Kaggle]( https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset).  The source of the data is unknown and listed as "(Confidential Source) – Use for educational purposed".  

The dataset’s format is comma separated values.  The first row of the data contains the column name.

## Data Issues
The following are potential data issues.  They will not affect the author's ability to use this dataset for learning about machine learning.  These issues would need to be addressed if this model were to be used in a production setting:
1. It is unknown if the gender recorded is the biological sex of the individual.
2. It is unknown if the hypertension indicator means the patient was ever diagnosed with hypertension and is currently under treatement or not, to the point they no longer experience the symptoms of hypertension.
3. Work type allow allows for one classification.  A person may interpret this differently.  Certainly a stay at home mother may eventually get a job, or be self employed while she takes care of the children.  A person could move from private, to government, to self employed work over the course of their career.
4. The definition of rural and urban is unknown.  This feature also doesn't indicate if it captures where the person currently lives.

## Data Security
There are no security concerns or requirements.  No personal identifiable information is present.  The author of this data has indicated it can be used for educational research.

## Counts
*	There are 12 features, including one response variable.
*	There are 5110 samples, not including the first row containing the header
*	There are 4861 samples with a negative response variable.
*	There are 249 samples with a positive response variable.
*	The relative ratio of positive/negative response variables is: 1/19.5

# Models
The response variable of interest is stoke.  Stroke classifies if the patient had a stroke (1) or never had a stroke (0).

## Metrics
The following are the initial thoughts on metrics that will be used to assess the value and/or impact of the model on the business. These concepts will be covered in Week 4 in depth, and these may chance significantly.

### High Level Value Statement
There appears to be some way of calculating the value of the model. Professor Spencer-Smith lectured that value is the best metric to use (not F0, AUC, RMSC). For this exercise a positive ROI would be a good goal for this initial assignment.

The value can be looked at from various stakeholders:

* Payers: Payers and insurance companies will want to significantly reduce the number of strokes. If they can identify members (patients) with stroke risks, they can educate and incentivize the member to reduce their stroke.
* People (patients/members): Strokes can be fatal or debilitating. People find value in staying healthy.
* Providers: Providers make money from strokes. They may be less likely to find value in preventing strokes as it will affect their revenue in a negative way.

### Confusion Matrix
I will build a confusion matrix.  A confusion matrix illustrates classifier performance based on true positive (tp), true negative (tn), false positive (fp) and false negative (fn) predicted values vs actual values.

|   | Actual Stroke |  Actual No Stroke |
|---|---|---|
| **Predicted Stroke** | TP  | FP  |
| **Predicted No Stroke** | FN  | TN  |

* True positive (TP): correct positive prediction
* False positive (FP): incorrect positive prediction
* True negative (TN): correct negative prediction
* False negative (FN): incorrect negative prediction

### Accuracy
Accuracy determines from all the classes (positive and negative), how many of them we have predicted correctly.  It will be calculated with: Accuracy = (TP + TN) / (TP + FP + FN + TN)

Accuracy will be used if there is an approximately equal members of each class.

### Precision
Precision determine from all the clases we have predicted as positive, how many are actually positive.  For example, it will tell what proportion of the patients we predicted would have a stroke, actually had a stroke.  It will be calculated with: Precision = TP / (TP + FP)

### Recall
Reccall will determine from all the positive classes, how many were predicted correctly. For example, the proportion of patients that actually had a stroke.  It will be calculated with: recall = TP / (TP + FN)

### Arithmetic Mean (F1 measure)
Will tell if the precision or recall is too small.  There should be a good balance between the two (i.e. one should be high and the other low).  The arithmetic mean will be calculated with: f1 score = (2 * Pecision * Recall) / (Precision + Recall)

### Area Under the Curve
Will look at the model across multiple conditions and allow the model to determine outcome based on different thresholds.  The calculation is not known at this point and will be filled in later.


# Timeline
This project will be completed over six (6) weeks, starting 5/10.  Assignments are due every Wednesday at 11:59PM.  

# Repo Structure
The repo is currently simple with one notebook, one README file, and one dataset.  It is unknown if this repo structure will contain multiple notebooks as the class progresses.
* stroke_preduction.ipynb: junipyer notebook
* heathcare-dataset-stroke-data.csv : The dataset described in [Data](#data) 
* README.md: This readme file.
* data_dictionary.csv: list of all features (columns / data points) and a description of each feature


# Getting Started

## Prerequisites
The project was built and tested using Google Collaboratory, aka: [Colab] (https://colab.research.google.com/).   Colab can be thought of as a Jupityer Notebook stored on a Google Drive.  Colab connects the notebook to a cloud-based runtime that can execute Python code without any required setup on a local machine. 

You will need to register an account in [Google Colab] (https://colab.research.google.com/).

## Built With
The following packages were used.  This project was tested on, and supported on, Google Colab.  There is no need to perform local package installations if Colab is used.  This section is used as a reference to find the relevant packages and supporting package documentation.
* [pandas]( https://pandas.pydata.org/)

## Installation (Opening)
 It may be possible to run this notebook/project locally, but the installation is not documented or supported.

1. Login to your Google Colab account
2. Select File->Open Notebook
3. Select "GitHub"
4. Enter the information required to open the notebook:
    * Username: matthewdheilmanvanderbilt
    * Repository: https://github.com/matthewdheilmanvanderbilt/CS5262_MachineLearning
    * Branch: Main
    * Select the notebook 'stroke_preditictoin.ipynb'

## Usage (Running)
1. There is a known issue with loading the dataset into the notebook.  This is being addressed.  The token may expire, and you'll have to regenerate it.  To do this, you'll have to go into the repo, view the raw file for the dataset, and then copy that URL into "Load Data section" at the following line:

```
responses = pd.read_csv('https://raw.githubusercontent.com/matthewdheilmanvanderbilt/CS5262_MachineLearning/main/healthcare-dataset-stroke-data.csv?token=GHSAT0AAAAAACCTI2NVNORWJRUX3JBHSGMUZDFSANA')
```

2. After the notebook has been opened, go to Runtime -> Run All

## Roadmap
- [x] Document Problem and find dataset
- [x] Create README
- [ ] Cleanse Data
- [ ] Exploratory Data Analysis
- [ ] Modeling
- [ ] Deploy

## Contributing
Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement". Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (git checkout -b feature/AmazingFeature)
3. Commit your Changes (git commit -m 'Add some AmazingFeature')
4. Push to the Branch (git push origin feature/AmazingFeature)
5. Open a Pull Request

# Resources
* **Python usage**: Whirlwind Tour of Python, Jake VanderPlas ([Book](https://learning.oreilly.com/library/view/a-whirlwind-tour/9781492037859/), [Notebooks](https://github.com/jakevdp/WhirlwindTourOfPython))
* **Data science packages in Python**: [Python Data Science Handbook, Jake VanderPlas](https://jakevdp.github.io/PythonDataScienceHandbook/) 
* **HuggingFace**: [Website](https://huggingface.co/transformers/index.html), [Course/Training](https://huggingface.co/course/chapter1), [Inference using pipelines](https://huggingface.co/transformers/task_summary.html), [Fine tuning models](https://huggingface.co/transformers/training.html)
* **fast.ai**: [Course](https://course.fast.ai/), [Quick start](https://docs.fast.ai/quick_start.html)
* **h2o**: [Resources, documentation, and API links](https://docs.h2o.ai/#h2o)
* **nbdev**: [Overview](https://nbdev.fast.ai/), [Tutorial](https://nbdev.fast.ai/tutorial.html)
* **Git tutorials**: [Simple Guide](https://rogerdudler.github.io/git-guide/), [Learn Git Branching](https://learngitbranching.js.org/?locale=en_US)
* **ACCRE how-to guides**: [DSI How-tos](https://github.com/vanderbilt-data-science/how-tos) 
* [Best Ever Readme] (https://github.com/othneildrew/Best-README-Template/blob/master/README.md)


# Contact Info
* Matt Heilman: matthew.d.heilman@vanderbilt.edu
* Project Link: [CS5262 Stroke Prediction with Machine Learning](https://github.com/matthewdheilmanvanderbilt/CS5262_MachineLearning))

# References
1.	https://www.cdc.gov/stroke/index.htm
2.	https://www.who.int/news-room/fact-sheets/detail/the-top-10-causes-of-death
3.	https://www.cdc.gov/stroke/facts.htm
4.	https://www.cdc.gov/vitalsigns/stroke/
5.	Strilciuc S, Grad DA, Radu C, Chira D, Stan A, Ungureanu M, Gheorghe A, Muresanu FD. The economic burden of stroke: a systematic review of cost of illness studies. J Med Life. 2021 Sep-Oct;14(5):606-619. doi: 10.25122/jml-2021-0361. PMID: 35027963; PMCID: PMC8742896.
6.	https://www.cdc.gov/stroke/prevention.htm



