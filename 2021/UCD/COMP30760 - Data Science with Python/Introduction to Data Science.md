---
tags: COMP30760 - Data Science with Python
---

# Lect 2, Introduction to Data Science

## The Big Data Era

- In the last decade, we've had witnessed an explosion in the production and availability of digital data
- "Information is the oil of the 21st century, and analytics is the combustion engine" - *Peter Sondergaard*
- **The 3 Bs:**
    - **Volume**: Huge volumes of data - terabytes or more
    - **Velocity**: Continueus streams o data arriving in realtime
    - **Variety**: Many different types of data - numerica data, structured text, unstructured text, images, video, audio, time series data
    - **Veracity**: Unceetain if data is reliable, noisy, or incorrect

## What is Data Science?
- Big data offers great potential, but...
    - How can we sift throguh massive amounts of noisy data to capture useful insights?
    - How can we quantify, interpret, and communicate those insights in a useful way?
- "A Data Scientist's real job is storytelling.. data gives oyu the want, but humans know the why" - Harvard Business Review, march 2013

### Definition:

- **Data Science**: Involves principles, processes, and methods for identifying and understandingmpehonena via the automate dor semi-automated analysis of data
- **Data Mining**: Extraction of knowledge from data, using algorithms that incorperate those principles
- Examples of common tasks:
    - Prediction
    - Regression
    - Clustering
    - Anomaly Detection
    - Visualization

## Basic Data Science Pipeline

- Data analysis projects typically invovle iterating through a pipeline of stpes. A simple data science pipeline consists of the following:
    - **Data acquisition:** Collect/import data from a variety of different sources
    - **Data preparation:** Clean, manipulate, and aggregate data into a fomr that can be analysed
    - **Analysis and Modeling:** Apply algorithms to explore relationships and make predictions
    - **Reporting & Visualization**: Interpret results, summarize, and present findings

## Knwoledge Discovering in Databases (KDD)

> Raw data /= valuable knowledge of actionable insights

- **KDD process**: Goal is to uncover useful knowledge hidden in large lower-level databses. This is achieved by applying data mining algorithins to identify and extract knowledge
- Human interaction is invovled throughout the process. The final step is to interpret the data

## CRISP-DM Model

- **Cross Industry Standard Process for Data Mining** introduced a standard model for the lifecycle of commerical data mining projects
- Business Unerstanding -> Data Understanding -> Data preparation -> Modeling -> Evaluation -> Deployment
- Designed to convert real-world business problems in data mining solutions
- Provides a structued approach to planning  aproject
- Emphasises the iterative nature of the data mining process

### Stages of CRISP-DM
1.  **Business Understanding**: What is the business problem?
2.  **Data Understanding**: What is th edata required to solve the business problem?
3.  **Data preparation**: Where is the data, how should it be collected, transofmred, and stored?
4.  **Modeling**: What data mining algorithms should be used to solve the business problem, given the data available?
5.  **Evaluation**: How well do the algorithms work?
6.  **Deployment**: How can the analytics results/model be integrated into the current workflow for the organisation?

> In this module, we will primarily focus on Steps 3-5: Data preparation, Modeling, and Evaluation

## Business Understanding

- Firstly a number of fundamental tasks needed to be completed ot convert a business problem into an analytics solution
    - What is the busines problem?
    - WHat are the goals  that the cusotmer really want sot achieve?
    - How does the business current work?
    - In what ways could a data analytics solution help solve the business problem?
- Next, we need to confirm that an analytics solution is feasabile in this scenario
    - Is th edata required by te solution availab eot us? Could it be made available?
    - What is the capacity of the business?

## Data Understanding

- **Data Understanding**: Start with initial data collection. Proceed with activities that enable us to beocme familiar with the data, identify data quality problems, discover first insights into the data, and find interesting subsets

## Creating Features
> Good input features are essential for analytics. Creating approprpate desriptive features can be difficult and is often the time-consuming part of developing an analytics soluton
- Three basic practical considerations are important when designing features
    - **Data Availability:** Do we have access to the data required to create the featur?
    - **Timing**: When will the data required for the feature be available?
    - **Longevity**: How long will the data be used in a feature stay relevant? Will it quickly become "stale" or inaccurate?
- Two further considerations have became increasingly important
    - What is the financially difficult will it be to create this data?
    - What are the privacy or ethical considerations?

## Feature Engineering
- Features in the ABT cna be of two types:
    - **Raw features**: These come directly from the original data
    - **Derived Features**: Do not exist in the original data, but are constructed in some way from the raw data
- **Feature Engineering**: Process of trnasofmring raw data into new features that better represent the task at hand
- Often has its own iterative process:
    - **Brainstorm features**
    - **Devise features**
    - **Select features**
    - **Evaluate Models**

