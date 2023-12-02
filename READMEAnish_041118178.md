# RiddikulusTech_Journey
welcome to my github repo.
One of the most common diseases in the world, diabetes is becoming more and more common. Although the exact etiology of diabetes is still unknown, researchers think that environmental lifestyle factors and genetics both contribute significantly to the disease. Diabetes is characterized by high blood sugar levels and impaired insulin production or utilization. It affects millions of people worldwide, leading to various complications such as cardiovascular diseases, kidney problems, and nerve damage. 
A few years ago research was done on a tribe in America which is called the Pima tribe (also known as the Pima Indians). In this tribe, it was found that the ladies are prone to diabetes very early. Several constraints were placed on the selection of these instances from a larger database. In particular, all patients were females at least 21 years old of Pima Indian heritage. Here, we are analyzing different aspects of Diabetes in the Pima Indians tribe by doing Exploratory Data Analysis and building a classification Model.
The overconcept opf this project is to load the dataset, learn about the dataset, visualize and train the model.
The first step is to load the python libraries and dataset in jupyter notebook. i loaded pandas, seaborn, matplotlib libraries first and then loaded the dataset.
The next step is to understand the dataset. To understand the dataset i uses various function like .describe(), .dtypes(), .head() , .shape() and more.
After i have basic understanding of the dataset next step for me is to Visualize. For visualization i use pairplot, boxblot, correlation matrix and distribution plot.
After visualization of the dataset, the next step for me is to model training for that i split the dataset into train and test.
I uses two Model Logistic Regression Model and Random Forest Model for train and testing the dataset.
I used these two model to find Accuracy, True Positives and True Negatives values.
Based on these three and overall accuricy from my point of view Logistic Regression Model is better then Random Forest Model.
The questions and answers are as follow

Qsn 1: Import the necessary libraries and briefly explain the use of each library
numpy use for numerical operations,
pandas use for data manipulation and analysis,
seaborn use for visualization,
pyplot used for visualization are the missing fields.

Qsn 2: Read the given dataset 
The read_csv is used to read csv file

Qsn3: The read_csv is used to read csv file
.tail(5) can be used for show last 5 dataset records

Qsn 4: Show the first 5 records of the dataset
.head(5) can be used for show first 5 dataset records

Qsn 5: Find the dimension of the pima dataframe. What do you understand by the dimension of the dataset?
.shape function is used to show/view dimension the diabetes csv or pima dataframe have 1000 rows and 9 column

Qsn 6. Find the size of the pima dataframe.
pima.size is used to determine the pima dataframe which is 9000 in size 

Qsn 7. Display the data types of all the variables in the data set?
pima.dtpes can be used to show all the data types. the dataframe have intiger and flot data type

Qsn.8 Are there any missing values in the pima dataframe? Which variables have missing values?
Ans 8:false means there is no value is missing. we can use isnull() to find null or messing values, but i used pima.isnull().values.any() function because it look for null value all over the dataset and return True or false output.

Qsn 9: Find the summary statistics for all variables except for  `'Outcome'` variable? Choose any one column/variable and explain all the statistical measures.
Ans 9: pima.iloc[:, :-1].describe() is used to describe every variable expect outcome. In this  Pregnancies have 
1000 count values, 
mean is 4.05100, 
standard deviation std is 3.325576
min is 0.00
25% (Q1): The first quartile or 25th percentile, separating the lowest 25% of 'Pregnancies' values is 1.
50% (Q2): The second quartile or median, separating the lowest 50% of 'Pregnancies' values is 3.
75% (Q3): The third quartile or 75th percentile, separating the lowest 75% of 'Pregnancies' values is 6.
max: The maximum value in the 'Pregnancies' column is 17.

Qsn 10: Plot the distribution plot for the variable 'BloodPressure'. Write your observations from the plot.
 i used sns.displot(pima['BloodPressure'], kind='kde')
plt.show() to show distribution plot  
In my observation the graph is skewed that means for certain age, bloodpressure count is rising and after that age blood pressure count is decreasing. Overall people between age 60 to 80 tends to have high blood pressure the other age group. for example people around 73 to 75 years have the high bloodpressure count. The bloodpressure count is rising around when people is reached 40 years of age and the bloodpressure count is declining after the age around 75.
Qsn 11: What is the 'BMI' for the person having the highest 'Glucose'?
The BMI for the person having highest glucose is 42.9

Q12.12.1 What is the mean of the variable 'BMI'?
12.2 What is the median of the variable 'BMI'?
12.3 What is the mode of the variable 'BMI'?
12.4 Are the three measures of central tendency equal?
Ans 12: 32.664772391408796 is the mean of the variable 'BMI'
12.2 32.2 is the median of the variable 'BMI'
12.3 32.0 is the mode of the variable 'BMI'?
12.4 The three measures of central tendency equal are not equal.

Qsn 13: How many women's 'Glucose' level is above the mean level of 'Glucose'?
449 is the toatal count of women glucose above mean level.

Q14: Create the pairplot for variables 'Glucose', 'SkinThickness' and 'DiabetesPedigreeFunction'. Write you observations from the plot.
Ans 14: sns.pairplot() can be used to show pairplot. The above pairplot shows pair and relations between three variables which are Glucose, SkinThickness and Diabetes Pedigree Function.The three variable are put in x axis and y axis in seperate pairplot box. 
We can analyze that all of the 3 variable are highly overlap with eachother.
When Glucose is increasing skin thickness is also increase and vice verca.
DiabetesPedigreeFunction and glucose are also positive related which mean if one value is increase another value will also increase and if decrease another value will also decrease.
skin thicknes and DiabetesPedigreeFunction are also directly related.
By using pairplot there is low chance of distinguish/seperate the variable.

 Q15. Plot the scatterplot between `'Glucose'` and `'Insulin'`. Write your observations from the plot.
 Ans 15:sns.scatterplot can be used for ploting scatterplot.
In the above scatterplot both insulin and glucose are correlated. When Insuline level is high glucose lebel is also high. And when glucose level drops insuline level also drop.

Q16. Plot the boxplot for the 'Age' variable. Are there outliers?
Ans 16:In this boxplot we can see there are many outliers beyond whisker.The median is around 30 and the boxplot is rightskewed.

Q17. Find and visualize the the correlation matrix. Write your observations from the plot.
Ans 17: The above heatmap shows corelation between 8 variables. Pregnancies ang Age is highly positevely corelated with value 0.55 and SkinThickness and Pregnancies is highly negatively corelated with coor value-0.08.

Q18. Split and scale the data
y = pima.BloodPressure
x = pima.drop('BloodPressure', axis = 1)
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X = scaler.fit_transform(x)
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y, test_size = 0.15,  random_state = 12345)

Q19. Train a Logistic Regression Model. What is the Accuracy and how many True Positives and True Negatives did you get?
Ans 19:Accuracy of Logistic Regression model on the train set: 11.18% Accuracy of the Logictic Regression model on the test set: 7.33% True positive is 0 True negatives are 10 The overall accuricy is 6.67% instead of using 2f i use 2% because it shows value in percentages.

Q20. Train a Random Forest Model. What is the Accuracy and how many True Positives and True Negatives did you get?
Ans 20:Accuracy of Random Forest model on the train set: 20.94%
Accuracy of Random Forest model on the test set: 6.00%
True positives are 0 and 
True Negatives are 7
And overall accuricy is 4.67%

Q21. Which model performed better
Ans 21:when, we look at accuricy logestic regression model is better then random forest model. Because logestic regression model provide 6.67% of accuricy whereas Random Forest Model provide 4.67% of accuricy. 
