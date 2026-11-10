# COMP-9170-Research-Method-Project
Fake News Detection and Media Trustworthiness: A Comparative Study of Explainable Machine Learning Models and Credibility Scoring


1. Introduction and Research Objectives
Fake news has become a serious problem as misleading information spreads rapidly through online news platforms and social media. It can influence public opinion, affect decision-making, and reduce public trust in reliable information sources. As the volume of online information continues to grow, manually checking the accuracy of every news article becomes increasingly difficult.
Machine learning and Natural Language Processing (NLP) offer methods for analyzing news content and identifying patterns associated with misinformation. However, predicting whether an article is fake or real is not enough. It is also important to understand why a model makes a prediction and how reliable that prediction is. In this project, we will compare two simple models, Multinomial Naive Bayes and Logistic Regression, to classify news articles as fake or real. We will also look at the words that affect their decisions and explore an article-level credibility score. If time allows, we may also test DistilBERT.
We want to answer the following research questions: 
1.	How accurately can Naive Bayes and Logistic Regression distinguish fake news from real news?
2.	Which words and linguistic features influence the models' predictions?
3.	Can calibrated model probabilities provide a useful article-level credibility indicator?
4.	How well do the models generalize across different news topics, and what biases may affect their predictions?

5.	
2. Dataset and Preliminary analysis
We used the Kaggle Fake and Real News Dataset (Bisaillon, n.d.). It has 23,481 articles in Fake.csv and 21,417 in True.csv. Both files include a title, article text, subject, and date. We found no missing cells. There were 5,573 repeated title-and-text pairs in the fake file and 220 in the real file. After removing exact duplicates from the combined data, 39,105 articles remained.
We also found a concern: the two files use different subject labels. Fake articles have labels such as News and politics, while real articles have politicsNews and worldnews. A model could learn these dataset differences instead of learning how to identify misinformation. We will therefore train with article text and check for topic, source, and duplicate-related bias.
