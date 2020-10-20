# Sentiment Analysis on Amazon Reviews

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/Amazon-5-Star-Review-Illustration.jpg)

I will be using Natural Language Processing (NLP) to perform sentiment analysis on reviews from Amazon, specifically from board games items. Because I enjoy playing board games, I figured it'll be interesting to incorporate something I enjoy with data science. As people are now showing their emotions through text data, sentiment analysis is becoming important for business as they can understand their customers better and see how well their products are performing. 

Amazon reviews provide objective feedback to a product summarized by the number of stars along with a review description. The number of stars is important as it tells us how well the product is doing and how the consumer feels about the product, but more importantly the value of the rating comes from the text in the review description. The goal of this project is to analyze and understand the underlying value of the text data by building a classification model that best predicts the most appropriate number of stars for each review.

In order to perform sentiment analysis, we need to understand the human language by analyzing text data. Though it is easy for humans to interpret the human language, there are limitations for computers when it comes to understanding human emotion such as sarcasm and irony. Fortunately Python contains libraries that help with NLP in which we will dive into for this project. By using sentiment analysis, I have created a model that best predicts a binary value of either good or bad for each Amazon review. In my model, reviews of 4-5 stars are classified as 'GOOD' reviews and 1-3 stars are classified as 'BAD' reviews. We will also explore how the model takes into account the importance of unigrams and bigrams and how it affects model performance.

**Results**


![](https://github.com/ttam37/dsc-mod-4-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/Content-based-filtering-vs-Collaborative-filtering-Source.png)

# File Description

* **csv_files**: folder containing all data files
    * items_df: general item information from search result page (scraped 10.13.20)
    * reviews_df: reviews for each item (scraped 10.13.20)
    * cleaned_items_df: preprocessed data of items_df
    * cleaned_reviews_df: preprocessed data of reviews_df
    * cleaned_cleaned_items_reviews_df: preprocessed data of both items_df and reviews_df
* **images**: folder containing all images for EDA and README
* **lexicon_English**: folder of files containing positive and negative words from Lexicon English
    * source: https://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html
* **web_scraping + preprocessing.ipynb**: notebook containing all web scraping and preprocessing
* **eda + feature_engineering.ipynb**: notebook containing all eda and nlp feature engineering
* **sentiment_analysis_model_1.ipynb**: notebook containing different implemented algorithms and accuracy results for model 1
* **sentiment_analysis_model_2.ipynb**: notebook containing different implemented algorithms and accuracy results for model 2
* **archived**: folder of archived files that were used for testing purposes throughout the project


# Technologies Used

**Python**
* Pandas for Data Cleaning & Data Manipulation
* Matplotlib, Seaborn for Data Visualization
* Numpy for Data Calculations
* BeautifulSoup for Web Scraping
* Scikit-Learn for Machine Learning algorithms
* Natural Language Toolkit (NLTK) for Natural Language Processing


# Web Scraping

All data were scraped from Amazon website. Since Amazon can detect scraper bots, I scraped several different times along so we don't slam the server and also used a VPN to prevent Amazon from blocking my IP address. Scraping Amazon was tricky as a lot of their product pages have different formats and structure making it hard to get the best data.

**General Item Example**
For search query 'board games' on Amazon, I scraped all item information from each search result page. Some data scraped include asin ID(product ID),title of the board game, average number of stars, and number of reviews.

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/general_item_data_from_search_page_screenshot.png)

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/items_dataframe_screenshot.png)

**Review Example**
For each item scraped, I scraped several pages of reviews that include the number of stars, review title, and review description.

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/example_review_screenshot.png)

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/reviews_dataframe_screenshot.png)


# Exploratory Data Analysis

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/count_of_user_ratings.png)

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/scatter_plot_avg_rating_and_price.png)

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/bar_plot_most_common_words_in_reviews.png)

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/wordcloud_most_common_words_in_reviews.png)

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/bar_plot_most_common_bigrams_in_reviews.png)

![](https://github.com/ttam37/dsc-capstone-project-v2-onl01-dtsc-ft-052620/blob/master/images/bar_plot_most_common_positive_negative_words_in_reviews.png)


# Modeling




# Final Results

The algorithm that gave me the best results is SVDpp, but because the test time was very large I instead made predictions using BaselineOnly algorithm. I created a personal user and based on the ratings, the model will recommended the highest rated movies (example below).

![](https://github.com/ttam37/dsc-mod-4-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/algorithm_best_rmse.png)
![](https://github.com/ttam37/dsc-mod-4-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/example_recommendations_baselineonly.png)




