# Personality-Prediction-Model-from-Portfolio
Myers-Briggs Personality Classification with ML algorithms


There are various tests that help to determine personality types such as the Big Five, Rorschach test, and MBTI test. In this project, prediction of personality is done by considering the MBTI test.

The MBTI personality classification system grew out of Jungian psychoanalytic psychology as a systematization of archetypal personality types used in clinical practice. The system is divided along four binary orthogonal personality dimensions, altogether comprising a total of 16 distinct persons.


### The dimensions are as follows

* Extraversion (E) vs Introversion (I): a measure of how much an individual prefers their outer or inner world.

* Sensing (S) vs Intuition (N): a measure of how much an individual processes information through the five senses versus impressions through patterns.

* Thinking (T) vs Feeling (F): a measure of preference for objective principles and facts versus weighing the emotional perspectives of others.

* Judging (J) vs Perceiving (P): a measure of how much an individual prefers a planned and ordered life versus a flexible and spontaneous life


#### The Database
* Student profile
* Answers given by students
* Instructor details
* Question details
* Answer details which comprises of possible answers and the right answer 


## Personality Test
Social media establishes uninterrupted connectivity, between its users and external world through revealing personal details and their viewpoints in every aspect of life. The focal aim of this here is to analyze how twitter (dataset) can be used to predict personality.
We show processes of developing  Machine Learning models on textual data. With this candidates can see their predicted personality types  according to Myers-Briggs Personality Types Indicator using their twitter user names since twitter is the classic entry point for practicing machine learning. With Twitter data, you got an interesting blend of data (tweet contents) and meta-data (location,hashtags, users, re-tweets, etc.) that opened up paths for analysis.
This training contains following topics:
* Exploratory Data Analysis
* Handling Imbalanced Dataset
* Vectorization of Text Data
* Model Creation
* Model Training
* Model Evaluation


### Dataset Description
The publicly available Myers–Briggs personality type dataset from Kaggle, containing 8675 rows
of data, was used in this research. In this dataset, each row consists of two columns. The first column
is for the MBTI personality type of a given person, and the second column includes fifty posts obtained
from the individual’s social media. Each post has been separated by three pipe characters . This data
has been collected from the users of an online forum, where in the first step, users take a questionnaire
that recognises their MBTI type; and in the second step, communicate with other users.

### Proportionality in the Dataset
In this step, matplotlib which is a Python 2D plotting library were used for data preview and to determine the distribution of the MBTI personality types in the dataset 
The image above show a non-uniform representation of MBTI types in the dataset that is not
commensurate with the actual proportions of MBTI types. As a result, it was clear that some cleaning in the dataset would be necessary in order to improve the
accuracy of the proportional representation of each MBTI type. 


### Categorization of Type Indicators in Four Dimensions

Four different categories were created for the type indicators in order to understand the distribution of types indicators in the dataset. 

The first category was for Introversion (I)/Extroversion (E), the second
category was for Intuition (N)/Sensing (S), the third was for Thinking (T)/Feeling (F)and the fourthcategory was for Judging (J)/Perceiving (P). As a result, for each category, one letter will return and at the end there will be four letters that represent one of the 16 personality types in the MBTI. For instance, if the first category is returning I, the second category is returning N, the third category is returning T and the fourth category is returning J, the relevant personality type would be INTJ.


### WordCloud of Frequently Used Words
Word Cloud is a data visualization technique used for representing text data in which the size of each word indicates its frequency or importance. Significant textual data points can be highlighted using a word cloud. Word clouds are widely used for analyzing data from social network websites. Word cloud was used to analyze the most frequently used words for each of the personalities.


### Pre-Processing the Dataset
As discussed earlier, data in this dataset was collected from an Internet forum and after analysing the content of the dataset, it was clear that some word removal is necessary. Non-uniform representation of MBTI types in the dataset that is not commensurate with the actual proportions of MBTI types in the general population was the most important reason for this. It was determined that this is because the
data was collected from an Internet forum created for discussion about personality type and MBTI
types were repeated too many times in the posts. This may also affect the accuracy of the model. As a
result, NLTK was used to remove the MBTI types from the dataset. After this step, the distribution
of MBTI personality types in the dataset was determined again. In addition, all urls and stop words were removed from the dataset. Finally, in order to
make the dataset more meaningful, the text was lemmatised, i.e., inflected forms of the words were transformed into their root words. Imbalanced data was also handled where the random over sampler function was used. This ensured that the categoraization of type indicatores in four dimenstions were balanced.


### Vectorise with Count and Term Frequency–Inverse Document Frequency (TF–IDF)
Sklearn library was used to recognize the words appearing  in the posts. It builds a vocabulary that only considers 100000 features ordered by term frequency in the dataset. In the first
step, posts were placed into a matrix of token counts. In the next step, the model learns the vocabulary
dictionary and returns a term-document matrix. The count matrix then transforms into a normalised
TF–IDF representation.

### Model Creation, Model Training and Model Saving

Models were created and predictions were made using the classification methods below: 

* Random Forest: Random Forest is a classification method that combines many decision trees based on individual sets of examples from the dataset. Each tree depends on the values of a random vector sampled independently and with the same distribution for all trees in the forest. In the Random Forest algorithm, the results of decision trees are combined to select the most popular class.

* Naive Bayes:  It is a classification technique based on Bayes' Theorem with an assumption of independence among predictors. Simply, a Naive Bayes classifier assumes that the presence of a particular feature in a class is unrelated to the presence of any other feature.

* Support Vector Machine: A support vector machine (SVM) is a supervised machine learning model that uses classification algorithms for two-group classification problems. SVM training algorithm builds a model that assigns new examples to one category or the other, making it a non-probabilistic binary linear classifier (although methods such as Platt scaling exist to use SVM in a probabilistic classification setting). SVM maps training examples to points in space so as to maximise the width of the gap between the two categories. 

* Decision Tree : It is a classification method where the paths from root to leaf represent classification rules. A decision tree is a flowchart-like structure in which each internal node represents a test on a feature, each leaf node represents a class label (decision taken after computing all features) and branches represent conjunctions of features that lead to those class labels. . 


* XGBoost : XGBoost (eXtreme Gradient Boosting) is a popular supervised-learning algorithm used for classification on large datasets. It uses sequentially-built shallow decision trees to provide accurate results and a highly-scalable training method that avoids overfitting.


### Performance Evaluation Metrics

The accuracy, precision, recall, f1-score and ROC area were the metrics used to evaluate the performance of the model. In the figure below, the metrics helps us determine the best classification algorithm to use for prediction of the different indicator types. From the results, in making prediction for the first category which is Introversion (I)/Extroversion (E), it is best to use the Random forest algorithm in the prediction. The random forest algorithm had an accuracy of 0.952 which exceeds all the other algorithms, hence the model is selected for prediction.
In making prediction for the second category which is Intuition (N) / Sensing (S), it is best to also use the Random forest algorithm in the prediction. The model had an accuracy of 0.993.
In selection of a model for the third category which is Judging (J)/ Perceiving (P), the XGBoost is the most preferred model to use due to its performance against the other classification models.
For prediction of fourth category which is Judging (J)/ Perceiving (P), the SVM is the most preferred model to use due to its performance against the other classification models.


### Usage of Models in Web Application

From training of the dataset, we were able to come to a conclusion on the best model to use in each dimension. By using pickle, the models are imported and used. The snscrape which is a scraper for social networking service is imported to scrape a user's tweets from their twitter account after the user has entered their username in the application. The Human Resource team requires all users to have a twitter account. Users are required to be engaging in tweets and post three hours before they take the personality test. 
The models are loaded, the users tweets are pre-processed and predictions are made thereafter.


### CV Analysis
Though curriculum vitae analysis is necessary to ensure recruiters do not miss good candidates or put forward incorrect candidates; but it is also important to process all applications quickly to ensure a fast response for clients and move to the interview and placement stages. In our project, our goal was to parse the entire CV and search for keywords from the CV.

For parsing CVs, we have used pyresparser which is a simple resume parser used for extracting important features such as name, email id, description, skills from CVs. Pyresparser supports PDF and DOCx files. 
