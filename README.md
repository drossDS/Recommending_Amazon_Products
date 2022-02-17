# Recommending Amazon Products

Using Recommendation System Techniques to Make Better Recommendations

# Background and Problem Statement
This relatively short weekly project was part of the recommendation systems module in the MIT Applied Data Science Program (MIT ADSP).  Data for over 7.8 million Amazon product reviews was provided and included the user ID, Product ID, and rating information from 1 to 5.  The task was to create a model which would recommend products to users using different recmmendation techniques.

# Initial Processing and Exploratory Data Analysis
After some initial examination of the data revealed that there were no missing values or null data in the provied data, a bar chart was plotted to determine the quanitity of each rating.  The number of unique users and umber of unique products were then extracted from the dataset, indicating that there were 4,201,696 users rating 476,002 unique products.  To simplify this task, a new dataset was derived with only products ratings only from users who have submitted 50 or more ratings.  This limit will ensure that each user has at least some information indicating the different products they have interacted with so that the recommendation systems can make more educated recommendations.  This reduced the size of the dataset drastically, with 1,540 unique users rating 48,190 unique products for a total of 125,871 ratings.  From here, a matrix of all 74,212,600 possible user/product combinations was created with the users comprising the rows and the products comprising the columns.  The provided ratings were popualted to their respective locations and the matrix denisty was calulated to be 0.17%, indicating that the matrix was very sparse.  For the vast majority of user/product combinations where a user had not rated a product, a value of 0 was imputed.

# Recommendation System Models

## Rank-Based Recommendation


## Collaborative Filtering


## Collaborative Filtering Using Singular Value Decompoisition (SVD)





# Note Regarding MIT ADSP Weekly Projects:
Due ot the relatively brief nature of program at only 12 weeks in duration, the code for this project was provided to the students in a near-finished state.  It was responsibility of the student ot then go through and fill in the sections of code relevant to the specific methods covered during the week's lesson.  As this course was designed for individuals from all professional backgrounds working full-time jobs, there was an emphasis on developing the student's intuition for how to use data science tools, and less on the details behind coding an entier project from scratch.
