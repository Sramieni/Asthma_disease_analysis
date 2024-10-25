# Asthma Disease Prediction Using Spark for Big Data Preprocessing and Statistical Analysis

## Introduction
This project explores the Asthma Disease dataset from Kaggle, containing health data for 2,392 patients. Our goal is to identify key factors contributing to asthma diagnosis and utilize Apache Spark for efficient data preprocessing and statistical analysis. By analyzing this dataset, we aim to uncover patterns that could aid in predicting asthma cases and help understand the role of lifestyle, environmental, and clinical factors in asthma. 

## Dataset
- **Source:** [Kaggle - Asthma Disease Dataset](https://www.kaggle.com/)
- **Details:** Contains demographic, lifestyle, and clinical data related to asthma.

## Project Implementation

### 1. Virtual Machine (VM) Setup
We set up and configured VMs using F5 Big-IP Edge VPN for secure access to the Michigan Tech network. The VM environment was configured with IP ranges, gateways, and DNS settings as specified. We used hadoop1 as the master node and hadoop2 as the worker.

### 2. Spark Configuration
1. **Installation**: Spark was pre-installed in /opt/spark.
2. **Cluster Configuration**: Defined hadoop1 as the master node and hadoop2 as the worker node in /opt/spark/conf.
3. **Starting the Cluster**: Spark master started on hadoop1 and workers on both nodes.
4. **Job Submission**: Used /opt/spark/bin/spark-submit to submit the main analysis script.

### 3. Data Preprocessing and Analysis

#### Missing Values
Missing values in key variables (Age, BMI, DietQuality, etc.) were filled with mean values, ensuring data consistency.

#### Encoding Categorical Variables
Categorical features were encoded to numeric values to make the dataset compatible with machine learning algorithms.

#### Scaling and Normalization
Continuous features were scaled to a range of 0 to 1 using MinMaxScaler, enhancing model performance.

#### Binning of Continuous Variables
Key continuous variables (Age, BMI, LungFunctionFEV1) were binned into quartiles to simplify analysis and interpretation.

#### Dataset Splitting
The dataset was split into training and testing sets with a 70-30 split for both classification (asthma diagnosis) and regression (lung function) tasks.

### 4. Statistical Analysis

#### Correlation Analysis
We performed a correlation analysis to examine relationships among continuous variables (e.g., BMI, LungFunctionFEV1). A heatmap visualized these correlations, aiding in understanding feature relationships.

#### Logistic Regression
Logistic regression was used to predict asthma diagnosis with an accuracy of 94.8% on both training and test sets, demonstrating the effectiveness of this model on the processed dataset.

#### Linear Regression
Linear regression was applied to predict lung function. The model achieved an R² score of 1.0, indicating high predictive accuracy, though potential overfitting may need addressing.

#### Chi-square Test
Chi-square tests were used to analyze associations between categorical variables (e.g., Gender, PetAllergy) and asthma diagnosis, revealing limited direct associations.

#### K-means Clustering
To identify patterns, K-means clustering segmented the data into three clusters, each representing different patient profiles based on age, BMI, and lung function, providing insights for potential personalized asthma management.

## Conclusion
This project demonstrated the effective use of Spark to handle and analyze large-scale health data. Despite some challenges with the VM environment, we efficiently processed the dataset, identified valuable patterns, and gained insights into asthma-related factors. This experience underscores the value of big data analytics in healthcare applications.

## Requirements
- **Software**: Apache Spark, Hadoop
- **Libraries**: Pandas, NumPy, Scikit-Learn, Seaborn, Matplotlib
- **Python Version**: 3.x

## Acknowledgments
- **Data Source**: [Kaggle - Asthma Disease Dataset](https://www.kaggle.com/)
- **Platform**: Michigan Tech Cluster

