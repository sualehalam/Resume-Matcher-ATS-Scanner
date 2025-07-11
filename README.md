# Applicant Tracking System (ATS) Resume Scanner
![FrontEnd Dashboard](https://github.com/user-attachments/assets/f1a01809-ffac-480e-957d-d297e74b464c)

## Introduction
A full-stack AI-driven ATS Resume Scanning Analysis Platform using Python, Flask, and NLP techniques to simulate intelligent candidate screening. Developed powerful information extraction pipelines to identify skills, quantify experience, and compute semantic match scores using custom scoring algorithms. Integrated dynamic Tableau dashboards and PDF reporting to visualize candidate-job alignment. Implemented advanced features like dark mode UI, skill tag rendering, and intelligent resume scoring logic. 



### Prerequisites
- [Pandas](http://pandas.pydata.org)
- [PyPDF2](https://pypi.org/project/PyPDF2/)
- [Flask](https://pypi.org/project/Flask/)
- [SciKit-Learn](https://pypi.org/project/scikit-learn/)
- [Dateparser](https://pypi.org/project/dateparser/)
- [ReportLab](https://pypi.org/project/reportlab/)
- [Werkzeug](https://pypi.org/project/Werkzeug/)

### Installing

Run the following commands on command prompt (as administrator) .

```
pip install pandas
pip install PyPDF2
pip install Flask
pip install scikit-learn
pip install dateparser
pip install reportlab
pip install Werkzeug
```

## Database Schema (Column Descriptions)
**1.	id:**
A unique identifier assigned to each entry in the database, representing an individual resume scanned by the ATS system.

**2.	name** The resumes file name of the candidate whose resume has been scanned by the system.

**3.	email**
The candidate’s email address, extracted automatically from the resume document.

**4.	phone**
The candidate’s phone number, parsed and extracted from the resume content.

**5.	skills**
A collection of skills identified in the resume, as extracted by the ATS scanner

**6.	score**
The ATS matching score indicating how closely the candidate’s resume aligns with a given job description. 

**7.	experience_level**
The candidate’s experience classification, derived from experience_years:  
Senior: ≥ 7 years  
Mid-level: ≥ 3 and < 7 years  
Junior: > 0 and < 3 years  

**8.	report**
The full, unstructured text extracted from the candidate’s resume.

**9.	experience_years**
The total number of professional experience years of candidate identified from the resume content.

**10.	skills_matched**
Represents the count of skills from the candidate’s resume that matched the required skills in the job description.


## Features of ATS Scanner
- Resume Parsing and Keyword extraction 
- Skill & Experience extraction
- Match Scoring Calculation
- Tag-style skill visualization
- Dark mode UI toggle
- Tableau Dashboard integration
- Downloadable ATS PDF Report 

## Resume Score Calculation
![Summary of ATS scoring calculation](https://github.com/user-attachments/assets/8209c3f0-c526-4f94-b37c-f5402520afbf)



## Tableau Dashboard Preview
[**Live Tableau Dashboard**](https://public.tableau.com/app/profile/ashish.ashish3477/viz/Book1_17455698844530/Dashboard1)

------------------------
![Tableau Dashboard](https://github.com/user-attachments/assets/82fa7682-8067-451f-a88c-e836bf67f386)


## Results of Resume ATS Scanner
![Resume Report](https://github.com/user-attachments/assets/483d0c62-9ba3-4b45-8990-391ef8e140e2)

## Statistical Results Summary

### Multiple Linear Regression Summary

**AIC** Value of Final Model: **-152.3** The lower the AIC value is the better is the models performance.  

**$R^2$= 46.5%**

**$R^2_{adj}$ = 44.58%**

An R-squared of **44.58%** means that ~ **45%** of the variation in the outcome variable can be attributed to the model’s predictor(s).

### Logistic Regression Summary

**AUC (0.79):** AUC (Area Under the ROC Curve) of 0.79 indicates strong and acceptable performance for a machine learning classification model. 

**Overall Accuracy (70.2%):** Decent — the model is correct ~70% of the time.

**Sensitivity (45.5%):** This is low and problematic as it’s only correctly identifying 45.5% of the actual 1s (positives) that are hired for the job.

**Specificity (85.7%):** Pretty good as it’s doing well at predicting 0s roughly 85% of the time.


## Final Thoughts and Recommendations

**Feature Engineering:** Since resume data can be sparse, more sophisticated feature engineering might help improve performance. Consider extracting more meaningful features from the text (e.g. sentiment analysis) or exploring the potential impact of other factors such as education level or job title.

**Model Comparison:** While the linear models and logistic regression perform well, it might be worth comparing the results with machine learning models like Decision Trees, Random Forests, or Gradient Boosting (e.g., XGBoost) to see if they offer a significant improvement in predictive accuracy, especially for complex datasets like resumes.


## Future Work
1. Job Recommendation System 
2. Use Pretrained LLM Embeddings Sentence-Transformers (BERT-based)
3. Integrate AI (GPT-4/BERT)
4. Add Multi-Resume Support
5. Soft Skill Detection
6. Multilingual Resume Support
7. Integration with Multi-Industry Keyword Database

# Authors
[![](https://img.shields.io/badge/LinkedIn-%40Sualeh%20Alam-lightgrey?colorA=abcdef&logo=data:image/jpeg;base64,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)](https://www.linkedin.com/in/sualeh-alam/)
