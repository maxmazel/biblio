# Biblio - Book Recommendation System  
  
### Problem Statement:  
MGM Books, a brick and mortar bookstore, is attempting to recover from layoffs due to the COVID19 pandemic. Following guidelines set by the city and state for reopening adjustments have to be made. In order to reduce contact customer contact with staff, I was assigned to create an applet that functions as a book recommendation system. In place of the staff’s years of knowledge on book sales, a machine learning model will update its recommendations every time a customer rates a book. Using the cosine similarity trained to the extremely large Amazon Books reviews data set, a model will be created. As the customer rates a book, it will dynamically update the underlying model with new similar books. The reviews by the customer will then be saved in the data set so it can learn trends the more it is used. This applet will also have the ability to be used as a search engine to find similar books as well as a promotional targeting tool.

### Executive Summary  
The data that was used was downloaded from an Amazon review study done by Jianmo Ni, UCSD. Two different data sets were combined, one that had every customer book review between 2009 and 2018, and one with the book information that is associated with each book found in the review data set. This data included reviews and information on over 29million books and 54million individual reviews. In order to get the data set to only have reviews that would help the model that was being created, minimal review count and reviewer parameters were set.  
  
The minimum review count of a book was set to 500 hundred reviews. In my data exploration, I found that books that had less than that tended to have higher ratings due to biased circumstances such as fan clubs for a musician. The number of books a customer has reviewed was set to 10. This amount reflected the minimum number of books that a future application will require a user to submit in order to have a profile.  
  
Once the data set was created and reduced down to 3.4million reviews a pivot table was rendered with book title as the index, reviewer id as the columns, and review overall score as the values. This pivot table was then used as the vectors when creating a cosine similarity sparse matrix. I chose this metric because it returns a table that shows how similar the index items are given the input vectors. Given that this is an unsupervised model the quality is assessed by user interpretation and not an output metric.  
  
After the model was run, I was able to query the results by typing in the name of a book. Returned were books similar to the one I typed in as well as the cosine similarity score. Cosine similarity is an optimization metric which means the more similar an object is the closest to one it will be. The first record in the query was the query term with a score of one followed by books that were rated similarly to it. I confirmed that the results were in fact similar to every input I had put into it.    
  
### Table of Contents:  
 - **[Problem Statement](#Problem-Statement)**
 
 - **[Executive Summary](#Executive-Summary)**  
   
 - **[Data Dictionary](#Data-Dictionary)**

 - **[Data](#Data)**
 
 - **[Project Files](#Project-Files)**   

- **[Conclusions and Recommendations](#Conclusions-and-Recommendations)**  

- **[References](#References)**

### Data Dictionary:  
asin - ID of the product  
reviewerID - ID of the product reviewer  
title - name of the product  
feature - bullet-point format features of the product  
description - description of the product  
price - price in US dollars  
image - url of the product image  
related - related products  
salesRank - sales rank information  
brand - brand name  
categories - list of categories the product belongs to  
tech1 - the first technical detail table of the product  
tech2 - the second technical detail table of the product  
similar - similar product table
  
### Data:
The data sets used in this project can be found on https://nijianmo.github.io/amazon/index.html. I used the book review data and meta data that is associated with it to create my model. The data sets themselves are extremely large and will not be a part of my repository. If you would like to recreate the work I have done please download the data sets from the previously stated url. 
  
### Conclusion and Recommendations:  
Machine learning models can be used to accurately recommend that a customer inputs into a search bar given previous reviews of customers. This was shown by creating a cosine similarity sparse matrix using quality reviews/reviewers discovered in the Amazon book review data set. Using this model I recommend creating a reviewer algorithm that learns as it grows. This is accomplished by adding new users to the pivot table prior to the initialization of the model. Doing this will help the algorithm be more accurate and give better recommendations going forward.  
  
This project has inspired me to do further development using the model created. Not only can I use this process to create recommendations for other products, category agnostic, but I can create a weighted algorithm that returns books based on an input genre and price range. Doing this will automate the book-buying experience and reduce human interaction in bookstores. Bookstores were struggling prior to the pandemic and not needing a return in staff may help them stay afloat.  
  
Reversing the weighted review algorithm I created returns reviewers that are more likely to buy a book based off of their reviewing history. This can be used to accurately target customers for promotional emails when a new book comes out. This not only drives sales up but makes the promotional process a lot more efficient.  
  
Going forward I intend on making this model into an API that other bookstores, fictional and not, can use to help in this new world we are living in. Having other bookstores means more customers which means more user data. Having all of the new diverse users will help the model become stronger and will also be a great stream of revenue outside of book sales.  
  
### References:  
Source of Data:  
Jianmo Ni, Jiacheng Li, Julian McAuley  
Empirical Methods in Natural Language Processing (EMNLP), 2019  
https://nijianmo.github.io/amazon/index.html.