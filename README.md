# IMDB-Sentiment-Analysis-using-XGBoost

In this project we will construct a recurrent neural network for the purpose of determining the sentiment of a movie review using the IMDB data set. We will create this model using Amazon's SageMaker service. In addition, we will deploy the model and construct a simple web app which will interact with the deployed model.
Project Instructions

The deployment project which we will be working on is intended to be done using Amazon's SageMaker platform. In particular, it is assumed that we have a working notebook instance in which we can clone the deployment repository.
In the XGBoost notebook we transformed the data from its word representation to a bag-of-words feature representation. For the model we are going to construct in this notebook we will construct a feature representation which is very similar. To start, we will represent each word as an integer. Of course, some of the words that appear in the reviews occur very infrequently and so likely don't contain much information for the purposes of sentiment analysis. The way we will deal with this problem is that we will fix the size of our working vocabulary and we will only include the words that appear most frequently. We will then combine all of the infrequent words into a single category and, in our case, we will label it as 1.
Since we will be using a recurrent neural network, it will be convenient if the length of each review is the same. To do this, we will fix a size for our reviews and then pad short reviews with the category 'no word' (which we will label 0) and truncate long reviews.

