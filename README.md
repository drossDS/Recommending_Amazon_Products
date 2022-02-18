# Recommending Amazon Products

Using Recommendation System Techniques to Make Better Recommendations

# Background and Problem Statement
This relatively short weekly project was part of the recommendation systems module in the MIT Applied Data Science Program (MIT ADSP).  Data for over 7.8 million Amazon product reviews was provided and included the user ID, Product ID, and rating information from 1 to 5.  The task was to create a model which would recommend products to users using different recmmendation techniques.

# Initial Processing and Exploratory Data Analysis
After some initial examination of the data revealed that there were no missing values or null data in the provied data, a bar chart was plotted to determine the quanitity of each rating.  The number of unique users and umber of unique products were then extracted from the dataset, indicating that there were 4,201,696 users rating 476,002 unique products.  To simplify this task, a new dataset was derived with only products ratings only from users who have submitted 50 or more ratings.  This limit will ensure that each user has at least some information indicating the different products they have interacted with so that the recommendation systems can make more educated recommendations.  This reduced the size of the dataset drastically, with 1,540 unique users rating 48,190 unique products for a total of 125,871 ratings.  From here, a matrix of all 74,212,600 possible user/product combinations was created with the users comprising the rows and the products comprising the columns.  The provided ratings were popualted to their respective locations and the matrix denisty was calulated to be 0.17%, indicating that the matrix was very sparse.  For the vast majority of user/product combinations where a user had not rated a product, a value of 0 was imputed.

# Recommendation System Models

## Rank-Based Recommendation
This model is effectively a "Top Products" recommendtion algorithm  The average rating for all products was computed in order to establish a product ranking, and a function was defined to recommend the top user-specified number of products with a user-specified minimum number of product ratings.

## Collaborative Filtering
A function was defined which makes a specified number of product recommendations based on the top-rated porducts of users with similar product tastes.  A cosine similarity function was employed to calculate a "similarity score" which would act as a numberical comparison between an input user ID and all other user IDs to produce a ranked list of similar users.  The products rated by the most similar users - which were not already rated by the input user - are then aggregated until the desried number of product recommendations is reached.


## Collaborative Filtering Using Singular Value Decompoisition (SVD)

# Conclusions

# Personal Commentary - Additional Coding, Uncovering Peculiarities

## Bottom Line Upfront (BLUF):
- It can be shown that the SVD model is not producing useful results upon furhter inspection of the recommendations being made
- The SVD model needs to be re-done

This weekly project assignment was unlike the others in that there was very little emphasis on measuring the acccuracy of either the collaborative filtering or SVD models.  The only attempt that was made in the prvided code which attmepted to calculate the RMSE error between the predicted and observed average product ratings, and it yielded a completely arbitrary result given that it was compared to nothing else.  The real idication that somehting was wrong, was the printing of the first few perdicted product ratings and versus their observed prpoduct ratiings, and some of them seemed off.

( **Insert a pic of the table here** )

Digging furhter, I decided to examine one user to determine if the predictions for products which that individual rated matched their actual (observed) ratings.  They were not....not even close.  So then the next strategy was to see if this was a fluke for that one user or if this whole model missed the mark entirely, and to do that, one must determine the purpose of the SVD model which was to synthesize a rating of every product by every user.  A simple way to test this is to determine f there are more ratings 1 through 5 in the predicted dataset than in the observed dataset.  There were not....there were actually less....

# Note Regarding MIT ADSP Weekly Projects:
Due ot the relatively brief nature of program at only 12 weeks in duration, the code for this project was provided to the students in a near-finished state.  It was responsibility of the student ot then go through and fill in the sections of code relevant to the specific methods covered during the week's lesson.  As this course was designed for individuals from all professional backgrounds working full-time jobs, there was an emphasis on developing the student's intuition for how to use data science tools, and less on the details behind coding an entier project from scratch.
