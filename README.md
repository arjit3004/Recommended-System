Statistical Analysis on E-Commerce Reviews, with Sentiment Classification using Bidirectional Recurrent Neural Network (RNN)

## Abstract

Understanding customer sentiments is of paramount importance in marketing strategies today. Not only will it give companies an insight as to how customers perceive their products and/or services, but it will also give them an idea on how to improve their offers. This paper attempts to understand the correlation of different variables in customer reviews on a women clothing e-commerce, and to classify each review whether it recommends the reviewed product or not and whether it consists of positive, negative, or neutral sentiment. To achieve these goals, we employed univariate and multivariate analyses on dataset features except for review titles and review texts, and we implemented a bidirectional recurrent neural network (RNN) with long-short term memory unit (LSTM) for recommendation and sentiment classification. Results have shown that a recommendation is a strong indicator of a positive sentiment score, and vice-versa. On the other hand, ratings in product reviews are fuzzy indicators of sentiment scores. We also found out that the bidirectional LSTM was able to reach an F1-score of 0.88 for recommendation classification, and 0.93 for sentiment classification.

## Results

 The review texts and labels (*recommendation indicator*) in the [dataset](https://www.kaggle.com/nicapotato/womens-ecommerce-clothing-reviews) were partitioned in the following fashion: 60% for training dataset, 20% for the validation dataset, and 20% for the testing dataset. The sentiment label for each review text were tagged using [NLTK](https://www.nltk.org/)'s sentiment analyzer.

|Task|Test Accuracy|Test Loss|
|----|-------------|---------|
|Recommendation classification|~88.2678%|~0.572342|
|Sentiment classification|~92.8414%|~0.453205|

**Table 1. Test Accuracy and Test Loss using Bidirectional RNN with LSTM.**

|Class|Precision|Recall|F1-Score|Support|
|-----|---------|------|--------|-------|
|Not recommended|0.70|0.65|0.68|847|
|Recommended|0.92|0.94|0.93|3679|
|Average/Total|0.88|0.88|0.88|4526|

**Table 2. Statistical Report on Recommendation Classification using Bidirectional LSTM.**

|Class|Precision|Recall|F1-Score|Support|
|-----|---------|------|--------|-------|
|Negative|0.47|0.50|0.49|289|
|Neutral|0.31|0.18|0.23|22|
|Positive|0.96|0.96|0.96|4215|
|Average/Total|0.93|0.93|0.93|4526|

**Table 3. Statistical Report on Sentiment Classification using Bidirectional LSTM.**

The dataset used had an imbalanced frequency distribution for classes in *recommendation indicator*, and through NLTK sentiment analyzer, classes in review *sentiment*. It is noticeable that the model used had relatively better predictive performance towards the class with the highest frequency distribution, i.e. *recommended* and *positive sentiment*. 
