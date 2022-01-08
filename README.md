# Crimes-in-Israel
The data was scattered into 3 different .xlsx sheets . We had to go over and over these sheets and choose the relevant data for our analysis.
The crimes.xlsx was the main file for the analysis so, in order to transform it into a Dataframe and work with it “safely” we had to do some cleaning for empty cells and non-relevant columns.
The cities.xlsx file also had many columns each representing a feature for each city , we had to choose a target columns as being the demographics used later in combine with crimes data to do prediction work.

So , after cleaning the files we could build our data frames
To get a clear picture of the data we had to display it into tables and graphs in order to find a correlation between the different files and therefor conduct our research.
For example : in question 3 where we had to come up with a research question, we had to combine data frame the 3 different files.
During our work , we found out that crimes data affect pretty much the predictions when excluded from the training (Because demographics can`t help predicting total number of felonies for example in a year) 
So what we had to do is to combine the crimes data with demographics into training data and the labels were the total values for each city in years (2014-2018) 
After adding the crimes data to the training , we had a very pleasant results when performing a prediction for a certain city.   

# Clustering
Research Question: 
Does sex offense charges change by the city form and religion, whether it is a city, village or a kibbutz where the majority are Jewish or not Jewish?
We ran kmeans algorithm with the Residents form as a feature

Now that we have the labels for each code we can analyze the results we got:

**Cities with a Jewish majority are clustered together, and further clustered by its size:**
- From the labels of the codes, we can see that codes between 0-140 that are clustered together (colored green) belong to a Jewish majority areas with large number of population (more than 100,000), which means it's a large city
- while the second cluster (colored yellow) that ranges between 150-160 belongs to a Jewish majority with a population between 20,000 to 50,000, which means it's a medium sized city.
- the third cluster (colored blue) that ranges between codes 170-190 represents areas with a Jewish majority with a populations of 5,000 to 20,000(small cities).
**Cities with a Non-Jewish majority are all clustered together in one cluster(colored black)**
- codes that range between 250-290 which represent cities with a population between 2,000 to 100,000 are clustered together, which is less accurate from the clustering that we got for Jewish majority cities.
**At last, villages are  and Kibbutzes have an overlap and are clustred further**
- the areas with code 330 which represents Kibbutz are clustred into two clustres,one colored red with the hishest rates of sexual offenses, this cluster shows the highest rates of sex crimes compared to other groups, which means, in those areas, sex offenses are more likely to happen or **are more likely to be reported to the police** since not all sexual harassment are reported. 
- areas with codes 330 and 350 which represent Kibbutz and villages are clustred togther,colored orange, they represent the village Resident shape with Jewish majorties that also have high rates of sexual offenses.

# K-means clustering results
In a conclusion, women in villages and Kibbutz are either more likely to be sexually harassed, or more likely to report it, while in areas where it shows that the least rates of sexual crimes are in non-Jewish areas (clusters red and black), which means that women in those areas are either less likely to be sexually harassed or less likely to report it

# Does an extra feature from clustering affect the prediction ? 
We added an extra feature which represents the cluster each city belongs to and then we ran our algorithm once again (we choose Adaboost) and surprisingly the results were more accurate for 4 of 5 test cities but the 5th city the prediction was worse than running the model without the new feature.








