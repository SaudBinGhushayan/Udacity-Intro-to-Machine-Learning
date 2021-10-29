## Project Overview 
-----------------------------
In this project I'm going to apply unsupervised machine learning techniques to identify cutomer segmetns of a population that from the core customer base of a mail-order company 

#### Exploring the data
-------------------------
Udacity_AZDIAS_Subset.csv: Demographics data for the general population of Germany; 891211 persons (rows) x 85 features (columns).

Udacity_CUSTOMERS_Subset.csv: Demographics data for customers of a mail-order company; 191652 persons (rows) x 85 features (columns).

Data_Dictionary.md: Detailed information file about the features in the provided datasets.

AZDIAS_Feature_Summary.csv: Summary of feature attributes for demographics data; 85 features (rows) x 4 columns.

#### Preprocessing 
-----------------------------
- First I assessed the missing data in each column and defined a threshold if the column with missing data is more than the threshold then the column will be dropped
- encoding features:

__Re-Encode Categorical Features__

The columns that I'm going to leave is :

1- GREEN_AVANTGARDE

2- SOHO_KZ

For the OST_WEST_KZ column I'm going to re-encode it to holds numeric binary value
O : 0

W : 1

For The rest columns I'm going to drop them to reduce the calculation

__Engineer Mixed-Type Features__

For PRAEGENDE_JUGENDJAHRE column I added two new features decade and movement

decade encoding : time-interval values which 40s is 1940 , 50s is 1950 and so fourth

movement encoding : west/mainstream : 1 and east/avantgarde : 0

For CAMEO_INTL_2015 column I added two new features wealth and life_stage

**Wealth encoding :**

Wealthy Households : 11-15

Prosperous Households : 21-25

Comfortable Households : 31-35

Less Affluent Households : 41-45

Poorer Households : 51-55

**Movement encoding :**

Pre-Family Couples & Singles : 11 , 21 , 31 , 41 , 51

Young Couples With Children : 12 , 22 , 32 , 42 , 52

Families With School Age Children : 13 , 23 , 33 , 43 , 53

Older Families & Mature Couples : 14 , 24 , 34 , 44 , 54

Elders In Retirement : 15 , 25 , 35 , 45 , 55

For the LP_LEBENSPHASE_FEIN , LP_LEBENSPHASE_GROB and WOHNLAGE columns I decided to drop them

#### Feature Transformation
----------------------------------
- I chose to fill the missing entries using Imputer from sklearn with the median instead of filling them with the mean or the most frequent value because of our data is skewed and most our entires are between 1 to 15 so filling them with the mean will produce floats and filling them with the most frequent value may affect the clustering later

- To standarize all variances I applied StandardScaler after filling the missing values in our data I selected StandardScaler because it changes each feature column to mean of 0 and standard deviation of 1

#### Perform Dimensionality Reduction
------------------------------------
- I chose to reduce the dimensions by 22 columns and still gets a variance equals to above 90%

#### Clustering
----------------------


After at the scree plot I chose 17 to be the number of clusters

#### Apply All Steps to the Customer Data
-------------------------------------
- After clustering I applied all the cleaning and preprocessing steps to the customer dataset

#### Compare Customer Data to Demographics Data
------------------------------------

Cluster 5 which is overrepresented in customer data

we can say that cluster 5 :

1- financially interested

2- low-money savers

3- most of the customers are between 46-60 years old

4- customers are soically minded , dreamful and cultural minded

5- customers youth is the 90s

6- customers are less affluent household

7- customers are older families and mature couples

Cluster 15 which is underrepresented in customer data

we can say that cluster 15 :

1- people are above 60 years old

2- people are not financially interested and not home oweners

3- people are family mined , religious and traditional minded

4- people's youth is the west and in the 50s

5- people are poorer households and elders in retirement

# license and credits 
------------------------------
Credit are given to Udacity for allowing this project to be completed, the data was provided by Bertelsmann partners AZ Direct and Arvato Financial Solutions 





