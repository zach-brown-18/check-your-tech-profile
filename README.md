# Tech Job Recommender
##### Nolan Arendt, Zachary Brown, Albert Frantz
--- 
## Goal
Make the transition into the tech industry less intimidating by matching unemployed individuals to their best fit in tech.  

---
## What this project does
Determine the best approach to building a recommender system that pairs job seekers with the job title they match best, based on a job seeker’s LinkedIn profile.  

---

## Table of contents
| File Name                      | Description                                                                                       |
|--------------------------------|---------------------------------------------------------------------------------------------------|
| [01-eda-jobs-data.ipynb]("code/01-eda-jobs-data.ipynb")                   | Job postings data cleaning process. Final cleaned job posting data export                         |
| [02-process-linkedin-data.ipynb]("code/02-process-linkedin-data.ipynb") | Cleaning linkedin profile data into  a single dataframe. Exporting final linkedin user dataframe. |
| [03-CVec.ipynb]("code/03-CVec.ipynb")                  | Recommender system - CVec process                                                                 |
| [03-Spacy.ipynb]("code/03-Spacy.ipynb")                 | Recommender system - SpaCy process                                                                |
| [03-TfidfVectorizer.ipynb]("code/03-TfidfVectorizer.ipynb")       | Recommender system - TfidfVectorizer                                                              |
| [03-KNN.ipynb]("code/03-KNN.ipynb.ipynb")                   | Recommender system - KNN                                                                          |

| Data                                  | Description                      |
|---------------------------------------|----------------------------------|
| [dice.csv]("data/dice.csv")                          | original Kaggle job posting data |
| [job_postings.csv]("data/job_postings.csv")                  | Cleaned version of the dice.csv  |
| [Albert_LinkedInData.csv]()           | Albert example linkedin data     |
| [Nolan_LinkedInData-12-16-2020.csv]() | Nolan example linkedin data      |
| [Ye_LinkedInData.csv]()               | Ye example linkedin data         |
| [Zach_LinkedInData_12-16-2020.csv]()  | Zach example linkedin data       |

---

## The Data
We used two sets of data for this project. The first was a kaggle dataset that included over 20,000 job postings with information on job title, job description, required skills and more. We used this dataset to calculate the cosine similarity score between this dataset and the second dataset that was our linkedin data. The linkedin data was downloaded from our individual profiles and processed and unpacked into a single dataframe using python. Ultimately these datasets allowed us to build a recommender system that matched people to their most suited tech job title. 
 
---
## Cleaning the Job postings datasets
To start the jobs dataset had 21919 total observations.  

We began by removing “fluff” from our text data. This general “fluff” included things like special characters, phone numbers, and emails that we determined would not assist in making job predictions. Some posts also had repeated information that was cleaned. Duplicate posts were dropped in cases that all columns were the same.  
  
Next, we categorized job titles into more generalized categories. Our goal was to give people a general sense of the jobs they should be looking at rather than specific jobs. For example “SQL developer” became “developer”. The 13 general job titles we were left with were: Analyst, Administrator, Consulting, Data Position, Designer, Director, Developer, Engineer, Programmer, Manager, Technician, Architect, and Support.  
   
We also categorized location into four general US specific areas. Those areas were Northeast, Midwest, Southern and Western. Location was categorized by the state of the posting. Similarly, we categorized job type into three categories: Full Time, Contract and market dependent positions.  
  
In the end our final cleaned jobs dataset had 16432 observations.  

---

## Recommender System
To best match people to the tech job title that best fits their Linkedin profile we used recommender systems. We produced three recommender systems based on three different techniques: Count Vectorization, KNN and SpaCy.  
  
Ultimately we found that the Count Vectorization model appeared to perform the best.  

---
## Software requirements
conda, pandas, numpy, re, httpimport, sklearn, IPython, SpaCy (and en_core_web_lg model)

---
## Sources
Kaggle Dataset: https://www.kaggle.com/PromptCloudHQ/usbased-jobs-from-dicecom  
LinkedIn User Data: https://www.linkedin.com/in/user_data  
Reddit Visualization Unemployment Claims: https://www.reddit.com/user/DorsaAmir/  

