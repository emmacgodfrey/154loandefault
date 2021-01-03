# 154loandefault
154 Loan Default Project Repo 

Please see '154Project1 (1).pdf' for a complete analysis. This was a group project, however all of the attached code is my own. 

The goal of this project was to predict whether a borrower would default on their respective loan. Default prediction is vital to protect banks against possible losses. While banks aqcuire revenue through interest, the benefit of the interest revenue diminished quickly when weighted against the cost of a possible loan default. Therefore, it is important for banks to have models with high prediction accuracy. 

This project was originally posted on Kaggle, however we attempted the challenge at a later date. The data is comprised of survey-data, so there is both a plethora of missing values and perhaps self-selection bias. 

First, due to the many NAs within monthly income and number of dependents, we sought to see whether these values were missing at random (MAR) or not missing at random (NMAR). To do so, we looked at patterns between the NAs and other variables; only debt ratio showed an interesting pattern with monthly income. However, we note that debt ratio is a function of monthly income, and thus high debt ratios for missing monthly income could still indicate MAR. Next, we performed MICE imputation to resolve the missing values. After imputation, our focus was on the imbalance of the dataset; there are many more people who pay back their loans than default. Our main technique to achieve balance was minority oversampling and synthetic generation of minority observations. Following this, we performed both CART and XGBoost to model the probability that a borrower would default. Ultimately, XGBoost performed best on the testing data on the basis of area under the receiver operating curve. 
