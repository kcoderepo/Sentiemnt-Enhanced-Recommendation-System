# Sentiemnt-Enhanced-Recommendation-System

This repository contains implementation of book recommendation system using NLP.
User based Collaborative Filtering is applied using surprise Library to get the prelimnary list of recommendations (20 books). 
KNNWithMeans turned out to be the best alogrithm. 

Sentiment analysis is applied to reviews of books from the recommendation list to get more
personalized recommendations for a given user. VADERSentiment (Valence Aware Dictionary and Sentiment Reasoner) analyzer is used. 
Computed the sentiment score for each review to filter out the top 10 book recommendations for the given user.

Steps involved in sentiment analysis:
<ul>
<li>Detecting language of reviews</li>
<li> Translating to English</li>
<li> Removal of stopwords</li>
<li> Predicting the sentiment of review as positive, negative and neutral</li>
<li> Calculating Sentimental score (-1,1) for each review</li>
<li> Group by on book_id and aggregated the sentimental score</li>
</ul>

The top 10 books are suggested as recommendations.

<b>Dataset Used</b><br><br>
Goodreads books dataset for Comic and Graphics Genre.<br>
Type: JSON files
Sources:
<ul>
<li> Goodreads books dataset:
https://drive.google.com/uc?id=1ICk5x0HXvXDp5Zt54CKPh5qz1HyUIn9m (89,411
books, 0.08 million entries, 353 MB)</li>
<li> Goodreads interactions dataset: https://drive.google.com/uc?id=1CCj-
cQw_mJLMdvF_YYfQ7ibKA-dC_GA2 (7,347,630 interactions, 7.3 million entries, 2.51
GB)</li>
<li> Goodreads reviews dataset:
https://drive.google.com/uc?id=1V4MLeoEiPQdocCbUHjR_7L9ZmxTufPFe</li></ul>

All the above datasets were pre-processed individually to retain the required features. The datasets were then merged to get an integrated dataset. The merged dataset is .csv
file.<br>
As the dataset was huge the code is run on HPC.
