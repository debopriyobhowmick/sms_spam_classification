# sms_spam_classification
This repository contains a classification model to identify spam messages a database of SMS. 

# Spam Classification

This project aims to classify a set of messages into spam or not spam (also called ham) using a Naive Bayes Classifier algorithm. 

The open-source data set is extracted from machine learning repository archives @ [UCI SMS Spam Collection](https://archive.ics.uci.edu/dataset/228/sms+spam+collection). 

This interactive Python notebook walkthroughs the cross-industry standard data science practices ([CRISP-DM](https://en.wikipedia.org/wiki/Cross-industry_standard_process_for_data_mining)) utilized to create, test, and optimize a naive Bayes classification algorithm. 

This notebook section discusses the end-to-end methodology used to create this classifier. 

1. EDA : Exploratory Data Analysis
2. Cross Validation : Splitting Training and Test Data 
3. Data Cleaning : Natural Language Processing
4. Model Development : Naive Bayes Classifier
5. Testing Model Performance


#EDA : Exploring the Dataset

## Key Highlights

1. The data set is sourced from machine learning repository archives @ [UCI SMS Spam Collection](https://archive.ics.uci.edu/dataset/228/sms+spam+collection), made available by Tiago Almeida and Jos Hidalgo. It is a classic vanilla use case for learning Naive Bayes Classifier from scratch. 

2. The dataset is contains 2 key pieces of information of 5572 text messages. One is is the text message itself (**SMS**) and another indicator variable to identify whether it is a spam or a ham. (**Label**).

3. **Label** is our outcome variable and **SMS** is our predictor variables. We have to utilise some standard cleaning and feature engineering practises to extrapolate more information from the only predictor Variable available to us.  


Given the above data we want to predict if a given sms is **spam** or not (aslo called **ham**).
One way to think about this problem is using Bayes' Theorem. In terms of probability we want to find out the $P(Spam | SMS)$


P(Spam | SMS) = {P(Spam) /P(SMS|Spam) } {P(Spam) P(SMS|Spam) + P(Ham) P(SMS|Ham)}
where $P(Spam)$ and $P(Ham)$is the prior probability of an sms being spam, which can be directly calculated from the count of spam/ham messages by the count of total messages. This is calculated below.
