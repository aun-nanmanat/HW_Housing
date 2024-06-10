# Housing

In this homework you will model and predict the rent of flats and houses. 

**Create a quarto document** and write your solutions into that document such that the rendered html-file is **"human-readable"**. That means meaningful headlines, well-prepared graphics, code folded, no clutter of code output, and some short text introducing and concluding the different exercises. 

Find the first exercises below.   

**Watch out:** More exercises will appear here later in new README-files! You will extend your analysis in the same quarto document. 
Finally, you have one html-file with all analyses. 


# Exercises

1. Get the dataset for houses and flats in Delhi from Kaggle:    
https://www.kaggle.com/datasets/goelyash/housing-price-dataset-of-delhiindia
Download the csv file and store it in a folder other than your project repository, so that you don't upload it to GitHub.  
Load it into R and have a look at the different variables.
2. **Pre-processing**
    1. **Units**  
The units used for financial and space variables are not very intuitive for continental Europeans.
Unfortunately, the data set does not come with a description.  
Find the source from where the original data came.  
Convert the values to continental European formats based on meters and Euros.  
(check these websites:  www.magicbricks.com; https://housing.com/calculators/square-feet-to-square-meter)
    2. **NAs**  
Check if the variables have missing values.  
Some variables with missing values are count variables.  
Think about whether you can safely replace the missing values with 0.  
Make a decision, write down the pros and cons, and implement it.  
(the function `if_else()` in combination with `mutate()` may be helpful)
    3. **Log-transformation**  
    Create log-transformed versions of all the count variables we will use for the analysis (but not longitude and latitude). For variables that include the value 0, add 1 to avoid infinite values. Ignore the variable lift for the further analysis.
    4. **Split the data**  
Split the data into a training set and a test set.  
Chose a share for the training data between 55% and 80%, and give a reason why you choose it that way.  
Continue with exploratory analysis on the training set, and leave the test set aside for later.  
3. **Exploratory analysis**
    1. **Mapping space and price per m2**   
    Create a map that gives us an overview of the price by square meter in different areas of the city. Make a scatter-plot of longitude and latitude, assign color to the price, and choose meaningful colors. 
Try one map with color assigned to the original price per m2, and one for the log-transformed version. Choose which you like better and explain why.   
Do a similar map with the size of the apartments and houses.  
What do these maps tell you?
    2. **Categories and price**  
Make a series of box-plots that illustrate differences in prices between:  
Houses and flats, new properties and resales, furnished or not, and ready or under construction.  
Decide which variable you want to use (price or price/m2, normal or logged) and explain why.  
Based on the results, what may be a good strategy to save money?
    3. **Size and price**   
Make a scatter plot illustrating the connection between the size of an apartment and the total price. Color the points according to price/m2. 
Then, add two regression lines for places with and without parking space available. (there are various elements in the geoms you can assign colors to). Provide informative descriptions for the axes and both parts of the legend.  
Make a similar graph with the logs of the area and price variables.  
How do the graphs differ?  
Which do you think is more informative?   
Why?  
Do the same again, but this time check for the availability of a balcony.
