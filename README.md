# MoodMaster-DSA
This project performs sentiment analysis using a custom implementation of the K-Nearest Neighbors (KNN) algorithm on a dataset of tweets. The dataset is split into training and testing sets. The algorithm classifies each tweet in the testing set based on the sentiments of the K nearest neighbors in the training set.

## Requirements

To run this project, you will need the following:

- Python 3
- Jupyter Notebook
- Pandas
- Scipy

## Installation

1. Clone this repository to your local machine.
2. Install Python 3 from the official website: https://www.python.org/downloads/
3. Install Jupyter Notebook by following the instructions here: https://jupyter.org/install
4. Install the required libraries by running the following command in your terminal: `pip install pandas scipy`

## Usage

1. Open the Jupyter Notebook.
2. Navigate to the directory where you cloned this repository.
3. Open the `main.ipynb` notebook.
4. Follow the instructions in the notebook to run the code and analyze Twitter sentiment data.

## Components

`Tweets.csv`: This file contains the training set of tweets. The tweets are labeled with positive, negative, or neutral sentiment.

`Tweets_Test.csv`: This file contains the testing set of tweets. The tweets are labeled with sentiment. The KNN algorithm will also classify each tweet in this file. Then the original sentiment is used to be compared to the predicted ones to check the accuracy of the algorithm.

`main.ipynb`: 
- The main file that contains and applies the KNN algorithm.
- **Preproccess**: The tweets in both the training and test data are preprocessed to remove noise, such as URLs, mentions, and hashtags,
- **Bag of Words**: Unique words are stored to a list from the training and the test dataset for later use.
- **Frequency Matrix**: It finds the **frequency** of words in training and the test data set using the unique words, then calculates the **euclidean distance** between every word in a sentence of the test dataset against every wordsentence in the training dataset using `cdist` function from the `scipy` library.
- **KNN Model**: Takes the euclidean distance for every sentence and sorts it using the `index_sort` function and slies the first `k` indices. Then it finds the sentiment on those indices in the training dataset. Then the majority sentiment label of the k nearest neighbors is then assigned as the predicted sentiment label for the test tweet.
- Evaluation Metrics: The accuracy of the k-NN model is evaluated using a confusion matrix including accuracy calculation.
- Note: The values of `k` can be changed according to the user. Different `k` outputs the different accuracy provided by the KNN Model.

## References:

- Damarta, R., Hidayat, A., & Abdullah, A. S. (2021). The application of k-nearest neighbors classifier for sentiment analysis of PT PLN (Persero) twitter account service quality. Journal of Physics: Conference Series, 1722(1), 012002. https://doi.org/10.1088/1742-6596/1722/1/012002

- Dutta Das, D., Sharma, S., Natani, S., Khare, N., & Singh, B. (2017). Sentimental Analysis for Airline Twitter data. IOP Conference Series: Materials Science and Engineering, 263, 042067. https://doi.org/10.1088/1757-899x/263/4/042067

- Fang, X., & Zhan, J. (2015). Sentiment analysis using product review data. Journal of Big Data, 2(1). https://doi.org/10.1186/s40537-015-0015-2

- Uddin, S., Haque, I., Lu, H., Moni, M. A., & Gide, E. (2022). Comparative performance analysis of K-nearest neighbour (KNN) algorithm and its different variants for disease prediction. Scientific Reports, 12(1). https://doi.org/10.1038/s41598-022-10358-x

    ### Dataset used:
- Twitter US Airline Sentiment. (n.d.). www.kaggle.com. https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment