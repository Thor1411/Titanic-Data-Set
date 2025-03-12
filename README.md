# Exploratory Data Analysis Using the Titanic Dataset
The Titanic dataset originally consisted of 1309 rows and 14 columns, as shown below:

![Initial DataFrame](images/Dataframe.png)

### Dataset Description

- **pclass:** Passenger Class (1 = 1st, 2 = 2nd, 3 = 3rd)
- **survived:** Survival (0 = No, 1 = Yes)
- **name:** Passenger Name
- **sex:** Gender (male/female)
- **age:** Age
- **sibsp:** Number of Siblings/Spouse Aboard
- **parch:** Number of Parents/Children Aboard
- **ticket:** Ticket Number
- **fare:** Fare
- **cabin:** Cabin Number
- **embarked:** Port of Embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)
- **boat:** Lifeboat (if survived)
- **body:** Body Number (if not survived and the body is recovered)
- **home.dest:** Home Destination

## Data Cleaning

The following data cleaning steps were performed:

- **Column Removal:**  
  Removed irrelevant columns for the analysis: `name`, `ticket`, `cabin`, `embarked`, `boat`, `body`, and `home.dest`.

- **Handling Missing Values:**  
  - Filled in missing values in the `age` column with the median age for the respective gender.
  - Filled in missing values in the `fare` column with the mean fare for the respective passenger class.

- **Duplicates:**  
  Checked for and removed duplicate records.

- **Outlier Detection:**  
  Examined the `fare` and `age` columns using box plots.

  ![Outliers](images/outliers.png)

  Although outliers are present in both the `fare` and `age` columns, they have been retained because they represent real-world variations (such as extremely wealthy passengers or very elderly individuals) and may hold meaningful correlations with survival.

- **Feature Engineering:**  
  Combined the `sibsp` and `parch` columns into a single, more informative feature named `is_alone`.

After these cleaning steps, the dataset was reduced to 1100 rows and 6 columns.


## Univariate Analysis

### Age Distribution
```
Mean: 29.8
Median: 28.0
Standard Deviation: 13.88
Skewness: 0.45
Kurtosis: 0.44
```
![Age Distribution](images/age_dist.png)

The Age distribution is right-skewed, suggesting that more young people traveled than older individuals.

### Fare Distribution
```
Mean: 36.93
Median: 16.1
Standard Deviation: 55.31
Skewness: 4.07
Kurtosis: 23.31
```
![Fare Distribution](images/fare_dist.png)

The Fare distribution is highly right-skewed, suggesting that the majority of passengers opted for cheaper tickets. The long right tail indicates that while most passengers paid lower fares, a smaller group paid significantly higher fares.

### Sex Distribution
```
Number of male passengers:  428
Number of female passengers:  672
```
![Sex Distribution](images/sex_dist.png)

More men were aboard than women.

### Passenger Class Distribution
```
Number of passengers in 1st class:  312
Number of passengers in 2nd class:  241
Number of passengers in 3rd class:  547
```
![PClass Distribution](images/pclass_dist.png)

Almost half of the passengers were travelling in 3rd class, while only a few were travelling in 1st and 2nd classes.

### Survival Analysis
```
Number of passengers who survived:  464
Number of passengers who did not survive:  636
```
![Survival](images/survival.png)

42.2% of passengers survived, while the rest perished in the tragedy.

### Travelling Alone?
```
Number of passengers who were not alone:  490
Number of passengers who were alone:  610
```
![Travelling Alone](images/travelling_alone.png)

55.5% of passengers were travelling alone, while only 44.5% travelled with family.

## Bivariate Analysis

### Passenger Class vs Survival

![pclass_vs_survival](images/pclass_vs_survival_bar.png)
![pclass_vs_survival](images/pclass_vs_survival_pie.png)

Passengers in elite classes exhibited a significantly higher survival rate compared to those in 3rd class, suggesting that priority may have been given to elite passengers during the rescue operations.

### Sex vs Survival

![sex_vs_survival](images/sex_vs_survival_bar.png)
![sex_vs_survival](images/sex_vs_survival_pie.png)

Female passengers exhibited a significantly higher survival rate (73.4%) compared to male passengers (22.3%), indicating that rescue operations have prioritized females.

### Age vs Survival
![age_vs_survival](images/age_vs_survival.png)

Children (0-20) and middle-aged (30-60) passengers experienced higher survival rates compared to young adults (20-30), while passengers aged 60 and above had the lowest survival rate. This pattern suggests that rescue efforts may have been influenced by age, potentially prioritizing the very young and middle-aged, while the elderly were at a distinct disadvantage during the tragedy.

### Travelling Alone? vs Survival
![alone_vs_survival](images/alone_vs_survival_bar.png)
![alone_vs_survival](images/alone_vs_survival_pie.png)

Passengers accompanied by family had a survival rate of 51.4%, compared to only 34.8% for those travelling alone. This suggests that the presence of family provided crucial support during the emergency, potentially leading to prioritized rescue efforts and improved survival odds.

