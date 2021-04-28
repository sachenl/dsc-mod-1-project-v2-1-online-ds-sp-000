# Module 1 Final Project


## The Project

Microsoft sees all the big companies creating original video content, and they want to get in on the fun. They have decided to create a new movie studio, but the problem is they don’t know anything about creating movies. They have hired you to help them better understand the movie industry.
Your team is charged with doing data analysis and creating a presentation that explores what type of films are currently doing the best at the box office. You must then translate those findings into actionable insights that the CEO can use when deciding what type of films they should be creating.

# The Questions

1. How does movie industry growth in these years? Print the graph of the domestic gross and foreign gross as well as the world gross for different years.
2. What is average rating as well as the gross earning for different category movies in histogram? Print out the relationship between rating and gross earning?
3. What is the total gross and rating of moives making in world for different genres? What is the distribution of top 200 movies which highest earned gross or highest rating. What is the number in 2018?

# The Dataset selection

To answer the last three questions, I select the data from the zipdata. After checking the data content, I selected data from three of the tables:
bom_movie_gross.csv
imdb.title.basics.csv
imdb.title.ratings



# Answer questions and make figures

### 1.  How does movie industry growth in these years? Print the graph of the domestic gross and foreign gross as well as the world gross for different years.

    For this question, I used the gross and year information from bom_movie_gross.csv. As in these data, the gross column is string, I coverted them to float value. During the convertion, I found some of them is not covertable as there is ',' in them, I polished all of them manually and filled all of the NAN cell with zeros. 
    
    I also add a new column world_gross which is the sum of domestic_gross and foreign_gross to check how the gross of movies in world wide.
    I then group the data by the different year and sum the number of gross in each column. 
    Finally, I plot the bar of total gross in each year of domestic, foreign and world side.
    
#### 2. What is average rating as well as the gross earning for different category movies in histogram? Print out the relationship between rating and gross earning?

    As there is no table contain the gross and rating information together, I need to combine the box. I then import the pandasql to merge the necessary tables.
    In this part, I genres data from IMDB_basics. As for most movies, there is multiple genres and some of the movies does not contain the genres information. So, I removed the movies which do not contain genres and then explode the genres to make each row containing only one genre. 
    The polished IMDB_basics was then merged with IMDB_rating with column tconst and make a new dataframe called combined_IMDB.  As the gross information in bom_movie_gross contains movie from 2010 to 2018, I removed the movie out of this range during merging. Nexed I combined the combined_IMDB with bom_movie_gross using the title in bom_movie_gross to match the primary title or original title in combined_IMDB. 
    After make the new dataframe, I then plot the scatter of average rating and world gross of each movie to check if there is any relation between rating and gross. 
    
#### 3. What is the total gross and rating of moives making in world for different genres? What is the distribution of top 200 movies which highest earned gross or highest rating? What is the number in 2018?   
    In this part, I want to make it clear if the world gross and average rating have any relation to the genres or not. So I first plot the box plot of world gross and average rating by the genres. 
    Since the average world gross are similar with each other but there are a lot of the movies had very high world gross in few of the genres. I then selected the top 200 movies base on the world gross and rating. Then I count the number of genres in the top 200 movies for gross and rating seperately. With these dataframe, I plot the bar of number of genres for every genre. 
    Next, I checked how does the market like in 2018. I then selected all the movies in 2018 and group by the genres. While grouping, I choosed to sum the world gross and average the rating for each of the genres. Finally, I plot bar of gross and average rating out for each genres.
    
#### Conclusion
    Finally, I found that, the Domestic gross of all movies did not change much from 2010 to 2018. However, the foreign and worldwise gross increased in general. The foreign market is larger than domestic market.
    The scatter of rating and gross earning for each movie from 2010 to 2018 shows that there is no obviouse relationship between the rowld gross and rating of the movies. However, most of the high earning movie had high rating more than 6 but less than 9. when rating is less than 4, the world gross of the movies is low too.
    The boxplot show that the medium value of world gross for each genres movies are less than 0.2e+09. In general, the top four genres based on gross are advaneture, animation, Sci-Fi and action. There are a lot of movies in these genres earned more than 0.6e+09 which is more than other genres. For the average rating, there is no signaficant different types of movies are higher than others. This suggests that, there is more chance to earn more money if we select movies in one or more of advaneture, animation, Sci-Fi and action genres.
    The histograms show that in the top 200 gross earning movies, more than 25% of them are adventure movies and more than 20% are action movies. In the top 200 rating movies, 25% are drama movies and 14% are documentary movies. action and adventure movies take abount 6%.
    In 2018, the average rating for different the genres are similar for all movies. The adventure and action earned more money than others.
    In general, the Adventure and Action movies earned more money than other types of movies. If we want to focus on the earning of the movies, choosing adventure or action or the mixuture types containing these genres is a good chocie. Also, the rating for these two types are above the average. If we want to focus only the high rating, seleting drama and cocumentary movies is good choice. 
    
    
    
    
    
    
    
    
    
