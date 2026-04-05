# Experiment 14 - Data-Normalization-and-Data-Type-Conversion

## Name - Falak Jain

## PRN - 25070123047

## Batch - ENTC A3 


## 🎯Aim - To learn  proper data normalization and data type conversion to ensure consistency, reliability, and efficient processing of data.

## ✅**OBJECTIVES** 
* Understanding Normalization Techniques</br>
* Categorical Data Encoding</br>
* Avoiding Multicollinearity</br>
* Hands-on Data Preprocessing on Real Datasets</br>

## ⚙️TOOLS
* **Python 3** — Primary language used for data manipulation and preprocessing</br>
* **Pandas** **(pandas)** — For creating and manipulating DataFrames, and applying get_dummies() for encoding</br>
* **NumPy** **(numpy)** — For numerical computations and array operations</br>
* **Scikit-learn** **(sklearn.preprocessing)** — Specifically LabelEncoder class for converting categorical labels into numeric form</br>

## 📊DATASET USED
* **Custom Product Dataset** — Manually created dictionary-based DataFrame (Laptop, Mobile, Tablet, etc.) </br>
* **Amazon Products Dataset (amazon_products_dataset_Expt-14.csv)** — 50-row CSV file with fields like Price, Rating, Units_Sold</br>
* **Student Dataset (Student-Dataset.csv)** — 10-row CSV file with fields like CGPA, Department, Placement_Status, Salary</br>
  
## 📚**THEORY** 
In real-world datasets, data is often collected from various sources and exists in different formats, scales, and types. Before applying any machine learning algorithm, it is essential to preprocess this raw data. Two of the most fundamental preprocessing steps: </br>
A. Data Normalization </br>
B. Data Type Conversion. </br>
These techniques ensure that the data is consistent, comparable, and suitable for further analysis or model building.</br><br>

### <ins>PART A : DATA NORMALIZATION</ins><br>
Data Normalization is the process of rescaling numerical data so that it fits within a specific range or follows a particular distribution. It prevents features with larger magnitudes from dominating those with smaller magnitudes during model training.</br>
### <ins>1. Min-Max Normalization</ins>
Min-Max Normalization scales the data to a fixed range, typically [0, 1]. It preserves the original distribution of the data and is useful when the algorithm requires bounded input values.</br>
#### FORMULA:</br>
#### X' = (X - Xmin) / (Xmax - Xmin)</br>
* **Xmin** = minimum value of the feature</br>
* **Xmax** = maximum value of the feature</br>
* **Result:** all values lie between 0 and 1</br>
### <ins>2. Z-Score Normalization (Standardization)</ins>
Z-Score Normalization transforms data so that it has a mean of 0 and a standard deviation of 1. It is useful when the data follows a Gaussian (normal) distribution and is preferred for algorithms like SVM and Linear Regression.</br>
#### FORMULA:</br>
#### X' = (X - μ) / σ</br>
* **μ** = mean of the feature</br>
* **σ** = standard deviation of the feature</br>
* **Result:** values are centered around 0</br>
### <ins>3. Decimal Scaling</ins>
Decimal Scaling normalizes data by dividing each value by an appropriate power of 10, such that the maximum absolute value becomes less than 1. It is the simplest normalization technique.</br>
#### FORMULA:</br>
#### X' = X / 10^j</br>
* **j** = smallest integer such that max|X'| < 1</br><br>

### <ins>PART B — DATA TYPE CONVERSION</ins> <br>
Machine learning algorithms work only with numerical data. However, many real-world datasets contain categorical (text-based) variables. Data Type Conversion refers to the process of transforming these categorical variables into numerical representations.</br>
### <ins>1. Label Encoding</ins>
* **Label Encoding:** assigns a unique integer to each category in a column. It is suitable for binary or ordinal categorical variables where the order matters.</br>
* **Limitation:** For nominal categories with no natural order, label encoding can introduce unintended ordinal relationships.</br>
### <ins>2. One-Hot Encoding</ins>
* **One-Hot Encoding:** creates a new binary column for each unique category in a variable. Each row gets a value of 1 in the column corresponding to its category and 0 in all others. It is used for nominal categorical variables.</br>
* **Limitation:** Can significantly increase the number of columns if a variable has many unique categories (known as the curse of dimensionality).</br>
### <ins>3. Dummy Encoding</ins>
* **Dummy Encoding:** is similar to One-Hot Encoding but drops one of the created columns using drop_first=True. This avoids the Dummy Variable Trap, where two or more columns become perfectly correlated (multicollinearity), which can negatively affect regression models.</br>
* **Limitation:** When **drop_first=True** is used, one category is dropped and treated as the reference/baseline category. This can sometimes make interpretation of results difficult, especially when all categories are equally important.</br><br>

### <ins>Key Features of Scikit-learn</ins>
* Simple and efficient tools for data mining and data analysis</br>
* Accessible to everybody and reusable in various contexts</br>
* Built on NumPy, SciPy, and Matplotlib</br>
* Open source and commercially usable under BSD license</br><br>

### <ins>Advantages of Scikit-learn</ins>
* **Consistent API** — All classes follow the same **fit(), transform(), fit_transform()** pattern making it easy to learn and use.
* **Pipeline Compatibility** — Preprocessing tools can be integrated into sklearn Pipelines, combining preprocessing and model training into a single streamlined workflow.
* **Handles Unseen Data** — Once fitted on training data, the same encoder or scaler can transform new unseen data consistently, which is critical during model deployment.
* **Scalability** — Works efficiently on both small and large datasets without requiring manual coding of transformation logic.
* **Well Documented** — Extensive official documentation and a large community make it easy to learn and troubleshoot.<br>

### <ins>API Methods</ins>
|Method|Description|
|:---|:---|
|fit(X)|Learns parameters (mean, min, max etc.) from the data|
|transform(X)|Applies the learned transformation to the data|
|fit_transform(X)|Performs fit and transform together in a single step|
|inverse_transform(X)|Reverses the transformation back to original values|
<br>

## 🌍**REAL-LIFE APPLICATIONS**


📊 Data Normalization (Scaling Data)


1. 🛒 E-commerce (Amazon, Flipkart)

 Product price = ₹100 to ₹1,00,000

 Ratings = 1 to 5

👉 Normalization ensures both features are equally important in recommendations.


2. 🏦 Banking & Loan Approval
   
Income (₹10,000–₹10,00,000)

Credit score (300–900)

👉 Normalization helps ML models fairly evaluate customers.


3. 🏥 Healthcare Systems
Blood pressure, sugar level, cholesterol all have different units

👉 Normalization helps in disease prediction models.


4. 🚗 Self-driving Cars
Distance, speed, object size

👉 Normalized data improves decision-making accuracy.


5. 📱 Social Media (Instagram, YouTube)
Likes, shares, comments vary widely

👉 Normalization helps ranking algorithms.


🔄 Data Type Conversion


1. 🛍️ Online Forms
   
 Age entered as "20" (string)

👉 Converted to integer for calculations

2. 💳 Payment Systems

Price stored as string "499.99"

👉 Converted to float for billing

3. 📊 Data Analysis (Python / Excel)

 Dates like "05-04-2026"

👉 Converted to datetime format for analysis

4. 🧾 CSV / Database Handling

 Numbers sometimes stored as text

👉 Converted for sorting, filtering, and computation

5. 🤖 Machine Learning
   
 Categories like "Male/Female"

👉 Converted to numeric (0/1) for models

## 💡**CONCLUSION**  
* Data normalization and categorical variable transformation techniques were successfully studied using various Python functions and operations.
* The preprocessing techniques and NLP techniques used for analyzing text data were studied successfully.

