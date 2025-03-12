# Titanic Dataset Exploratory Data Analysis (EDA)

This analysis explores the **Titanic dataset**, a historical dataset detailing passengers aboard the ill-fated RMS Titanic. The dataset provides various passenger details such as age, sex, class, survival status, and more. The goal of this exploratory data analysis (EDA) is to uncover patterns and relationships within the data, particularly those that influenced passenger survival.

## Dataset Overview

The Titanic dataset consists of **1309 rows** and **14 columns** with the following features:

- **pclass:** Passenger Class (1 = 1st, 2 = 2nd, 3 = 3rd)
- **survived:** Survival Status (0 = No, 1 = Yes)
- **name:** Passenger Name
- **sex:** Gender (male/female)
- **age:** Age
- **sibsp:** Number of Siblings/Spouses Aboard
- **parch:** Number of Parents/Children Aboard
- **ticket:** Ticket Number
- **fare:** Fare
- **cabin:** Cabin Number
- **embarked:** Port of Embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)
- **boat:** Lifeboat (if survived)
- **body:** Body Number (if not survived and body is recovered)
- **home.dest:** Home Destination

## Data Cleaning

The dataset was cleaned and preprocessed to ensure a meaningful and insightful analysis:

- **Column Removal:**  
  Irrelevant columns such as `name`, `ticket`, `cabin`, `embarked`, `boat`, `body`, and `home.dest` were removed to simplify the dataset and focus on relevant features.

- **Handling Missing Values:**  
  - Missing `age` values were imputed using the median age for the respective gender.
  - Missing `fare` values were imputed using the mean fare for the respective passenger class.

- **Duplicate Records:**  
  Duplicate records were identified and removed to maintain data consistency.

- **Outlier Detection:**  
  Outliers in the `fare` and `age` columns were identified through box plots. Although these outliers exist, they were retained as they represent real-world extremes, such as extremely wealthy passengers or very elderly individuals, which could offer valuable insights into survival patterns.

- **Feature Engineering:**  
  The `sibsp` and `parch` columns were combined into a new feature, `is_alone`, indicating whether a passenger was travelling alone.

After these steps, the dataset was reduced to **1100 rows** and **6 columns**.

## Univariate Analysis

### 1. **Age Distribution:**

- **Mean:** 29.8  
- **Median:** 28.0  
- **Standard Deviation:** 13.88  
- **Skewness:** 0.45 (slightly right-skewed)  
- **Kurtosis:** 0.44

The age distribution is right-skewed, indicating that younger passengers were more prevalent aboard the Titanic.

![Age Distribution](Images/agedist.png)

### 2. **Fare Distribution:**

- **Mean:** 36.93  
- **Median:** 16.1  
- **Standard Deviation:** 55.31  
- **Skewness:** 4.07 (highly right-skewed)  
- **Kurtosis:** 23.31

The fare distribution is highly right-skewed, with the majority of passengers paying lower fares, while a smaller group of passengers paid significantly higher fares.

![Fare Distribution](Images/faredist.png)

### 3. **Gender Distribution:**

- **Male Passengers:** 428  
- **Female Passengers:** 672

There were more female passengers than male passengers aboard.

![Sex Distribution](Images/sexdist.png)

### 4. **Passenger Class Distribution:**

- **1st Class:** 312  
- **2nd Class:** 241  
- **3rd Class:** 547

Most passengers were in 3rd class, followed by a smaller proportion in 1st and 2nd class.

![PClass Distribution](Images/pclassdist.png)

### 5. **Survival Analysis:**

- **Survived:** 464 passengers  
- **Did not Survive:** 636 passengers

42.2% of passengers survived, while the majority did not.

![Survival](Images/suvdist.png)

### 6. **Travelling Alone:**

- **Not Alone:** 490 passengers  
- **Alone:** 610 passengers

55.5% of passengers were travelling alone, while 44.5% were travelling with family.

![Travelling Alone](Images/alonedist.png)

## Bivariate Analysis

### 1. **Passenger Class vs Survival**

Survival rates were significantly higher for passengers in elite classes, suggesting that class may have influenced priority in rescue operations.

![Passenger Class vs Survival](Images/pclass-sur.png)  
![Passenger Class vs Survival](Images/pclass-sur2.png)

### 2. **Sex vs Survival**

Female passengers had a much higher survival rate (73.4%) compared to male passengers (22.3%), indicating that rescue efforts may have prioritized females.

![Sex vs Survival](Images/sex-sur.png)  
![Sex vs Survival](Images/sex-sur2.png)

### 3. **Age vs Survival**

Children (aged 0-20) and middle-aged passengers (aged 30-60) had higher survival rates than young adults (aged 20-30). Passengers aged 60 and above had the lowest survival rate, suggesting that age played a role in determining priority for rescue.

![Age vs Survival](Images/age-sur.png)

### 4. **Travelling Alone vs Survival**

Passengers travelling with family had a higher survival rate (51.4%) than those travelling alone (34.8%), suggesting that being accompanied by family could have increased the chances of survival.

![Travelling Alone vs Survival](Images/alone-sur.png)
