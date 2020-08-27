# Predicting Best Answer of Online Forum Questions

*Group 5: Amélie Pingeot, Youssef Jachttar, Qinjiong Zeng & Thomas Vermaelen* 

This is the final project to our class in Natural Language Processing. For this assignment we are tasked to predict the best answer 
for each question that was posted on an online forum. We are provide a dataset containing observations that consist of either questions, answers or comments. 
The variables include the observation id, parent id (for answer and comments only), the text, is_best_answer, category, date, just to name a few. 
Our final results reveal that Random Forest outperforms Logistic Regression in predicting the best answer, where AUC of RF = 0.99 and AUC of LR = 0.80 for the testing set.  

## Project Outline

### I. Convert Provided File Into Readable CSV File

This part consists of consolidating the text files that were provided into a single csv file 

### II. Data Preparation

• Out of about a million questions in total, we sample 100,000 questions/topic ids  
• We clean, tokenize and stem all the text  
• Fix the high-cardinality of the country variable by merging certain countries into one class  
• Create a table of answers related to our 100,000 questions that includes tokens for each answer's respective question and comments  
• Check the class distribution of the target variable "is_best_answer": we find that class "1" is highly under-represented (we will deal with this in the modeling part)  

### III. Modeling

• Perform 80/20 training and testing split  
• Dummify categorical variables  
• Also perform SMOTE to get 50/50 balance of the target variable  
• Scale the data  

#### A) Word2Vec

• We create vector embeddings to numerically represent the tokens from comments and questions using Word2Vec  

#### B) Logistic Regression

• Train AUC: 98%  
• Test AUC: 80%. 

#### C) Random Forest

• Train AUC: 100%   
• Test AUC: 99%  

#### D) Random Forest vs. Logistic Regression

• Visualize the difference between AUC curves for both Random Forest and Logistic Regression  
