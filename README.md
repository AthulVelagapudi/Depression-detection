# Depression-detection
Overview
1. Introduction
2. Method
3. Data set
4. Implementation
5. Results of analysis
6. Conclusion
7. Recources
## Project Motivation
Mental health deserves a great deal of attention and care,
considering how social media and its impact on depression
have evolved over the past few years, with various platforms
offering coping mechanisms such as #HowIFightDepression
on Twitter have helped numerous individuals to come out
and share their personal experiences, in a way, emotionally
uplifting each other. Most of humanity suffers from depression
in one way or another. Sentiment analysis provides us with
the polarity of a sentence i.e whether it is a positive, negative,
or neutral expression. Considering how depression plays an
important role in a person’s behavior, sentiment analysis can
help us get deeper insights as well as key emotional triggers
to understand the actual mood behind the text.

In this project, we aim to analyze and classify the sentiment
of the tweets from a custom-built dataset. the dataset consists
of 19000 tweets in which, there are 10000 positive tweets
obtained from the Sentiment 140 [7] dataset, and the remaining
9000 negative tweets involving keywords like anxiety and
depression were obtained from Twitter scraping using Twint
[5].
To classify the tweets we used a Naive Bayes [9] classifier
since our dataset was relatively small and considering we
require a reasonable response time, Naive Bayes was a perfect
choice.

Term Frequency- Inverse Document Frequency (TF-IDF)
[6] is a weight/ statistical measure used to denote how important a word is in a text. TF-IDF compliments the Naive
Bayes classifier since it guides the model to understand the
significance of the overall text based on their probabilities.

## Method
The main aim of the project is to build a machine learning
model which will predict whether a give tweet is a depressive
tweet or not a depressive tweet. To achieve this we used Naive
Bayes machine learning model which classifies the given text
into 2 categories (Depressed , Not Depressed).

Naive Bayes a classification method based on Bayes’ Theorem and
the assumption of predictor independence. A Naive Bayes
classifier, in simple terms, assumes that the existence of
one feature in a class is unrelated to the presence of any
other feature.The algorithm implementation is done base on
[10].Text classification and spam filtering are two areas where
the Naive Bayes Model excels. Working with the NB algorithm
has the following advantages: To learn the parameters, only
a little amount of training data is required. When compared
to more sophisticated models, they can be taught relatively
quickly.

## Dataset
The data set which is used for this machine learning model
is the combining part of the Sentiment140 [7] (10000 positive
tweets), and another one for depressive tweets (9000 tweets),
with a total of 19,000 tweets.Sentiment140 Kaggle [7]was
used to get 1,600,000 tweets for the Sentiment140 dataset.
The tweets have been annotated (0 means negative, 2 means
neutral, and 4 means positive) and can be used to determine
sentiment. For positive tweets, this data set is used.
The negative tweets are extracted with the help of twint tool
[5] with the key words as depression and anxiety.

![](https://github.com/AthulVelagapudi/Depression-detection/blob/main/images/twint.png)

These two data sets are combined after analysis and shuffled
data set is create which is used to train the machine learning
model.

![](https://github.com/AthulVelagapudi/Depression-detection/blob/main/images/merging%20data.png)

## Implementation

1. Preprocessing : Firstly the entire data set(19261 samples) is split into train data set (15413 samples) and test
dataset(3852 samples).Which is 80-20 train test split Then
Word cloud analysis is done to get gain insights about the
words which are dominating and the words which are spread
across the classes of the data set. The text is the processed
so that it can be given as an input to the machine learning
model The steps which are involved in preprocessing the
text are Tokenization the tweets, stemming of each token,
and removal of stop words which are present in the tokens
Tokenization is a process of converting the whole text into
small tokens which helps to sepearate each word in the given
text. Stemming is a technique for eliminating affixes from
words in order to retrieve the base form. Removal of stop
words is imporant cause these words doesnt really carry the
important information in the text
2. Model training: All the necessary packages are installed
in the environment. The naive bayes model class probabilities
are calculated using TFIDF as a statistical measure which is
used to know the importance of each word. After the model
is trained a pickle file is generated which is the actual trained
model used to classify the text.
3. User Interface: Basic UI is created with the help of
tkinter library of python where the user can type any text and
the model predicts whether the text is depressed or not

![](https://github.com/AthulVelagapudi/Depression-detection/blob/main/images/UI_with_code.png)

## Result of analysis
The results of implemented machine learning model and the
analysis done on the data sets are shown in this section.
1. Score
This model is evaluated based on the test set.
Precision,Recall,F-score and Accuracy of the model is
calculated which are above par.Few of the custom inputs are
tested to validate the results.

![](https://github.com/AthulVelagapudi/Depression-detection/blob/main/images/metrics.png)

2. Word clouds
Word cloud is a cloud filled with lots of words in different
sizes, which represent the frequency and the importance of
each word Word clouds are generated for each class and the
results show us that the words which often repeat in the positive class are: depression, mentalhealth, anxiety, self, disorder,
issue ... which are most likely associated with depression

![](https://github.com/AthulVelagapudi/Depression-detection/blob/main/images/positive_word_cloud.png)

the words which are often repeated in the negative class:
status, love, pic, know, today, live ... which are mostly not
related to depression. Here positive class refers to the class
which is classified as depressed and negative class refers to
the class which is classified as not depressed

![](https://github.com/AthulVelagapudi/Depression-detection/blob/main/images/negative_word_cloud.png)

3. Results
The final result is show as below where we give a text and
the text is classified as depressive text or not

![](https://github.com/AthulVelagapudi/Depression-detection/blob/main/images/result_Gui.png)

## Conclusion

In this report we have implemented a Naive Bayes model
to classify the polarity of tweets and uncover underlying
emotions with a custom build data set.The evaluation of the
model is done based on the f1 score of the model. This
model can be improved my taking another label which is a
neutral label(class) and training the model with data which is
more specific to depression context based tweet rather than the
tweets which are more based on depression key word specific.

## References
1. K. A. Govindasamy and N. Palanichamy, ”Depression Detection Using
Machine Learning Techniques on Twitter Data,” 2021 5th International
Conference on Intelligent Computing and Control Systems (ICICCS),
2021, pp. 960-966, doi: 10.1109/ICICCS51141.2021.9432203.
2. M. M. Aldarwish and H. F. Ahmad, ”Predicting Depression Levels
Using Social Media Posts,” 2017 IEEE 13th International Symposium
on Autonomous Decentralized System (ISADS), 2017, pp. 277-280, doi:
10.1109/ISADS.2017.41.
3. Tripathy, A., Agrawal, A., Rath, S. K. (2015). Classification of Sentimental Reviews Using Machine Learning Techniques. Procedia Computer Science, 57, 821–829. https://doi.org/10.1016/j.procs.2015.07.523
4. Alessa, A., Faezipour, M. (2018). Tweet Classification Using Sentiment
Analysis Features and TF-IDF Weighting for Improved Flu Trend
Detection. Machine Learning and Data Mining in Pattern Recognition,
174–186. https://doi.org/10.1007/978-3-319-96136-1-15
5. https://github.com/twintproject/twint
6. Kosasih, R., Alberto, A. (2021). Sentiment analysis of
game product on shopee using the TF-IDF method and
naive bayes classifier. ILKOM Jurnal Ilmiah, 13(2), 101–109.
https://doi.org/10.33096/ilkom.v13i2.721.101-109
7. https://www.kaggle.com/kazanova/sentiment140
8. Kim, S. W., Gil, J. M. (2019). Research paper classification systems
based on TF-IDF and LDA schemes. Human-Centric Computing and
Information Sciences, 9(1). https://doi.org/10.1186/s13673-019-0192-7
9. Farid, D. M., Zhang, L., Rahman, C. M., Hossain, M., Strachan, R.
(2014). Hybrid decision tree and na¨ıve Bayes classifiers for multiclass classification tasks. Expert Systems with Applications, 41(4),
1937–1946. https://doi.org/10.1016/j.eswa.2013.08.089
10. https://github.com/yonebayashi/nlp-twitter-depressiondetection/blob/master/Detect%20depression%20in%20tweets.ipynb
