
# Credit Risk Intelligence & Profit Simulation Engine 

## Objective

In the last 2 years the level of bad loans has increased, this is very bad for the condition of banks. The bank needs the right solution to handle the current bank situation. The bank asked to find out what caused the credit card incident and asked to create a model that can predict credit risk so that it can be handled appropriately.

![images](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/75a79d18-97b1-4a6d-8efa-0a242eaf02c7)




## Research Questions
"How do factors such as credit profile, economic stability, and customer credit management contribute to the rate of bad credit at a particular financial institution?"

## Data and Assumptions
The data used is
- Data from an ABC bank from 2007-2014.
- The dataset owned is a supervised learning dataset.
- The dataset contains 466285 rows and 75 columns
- Contains information about customer and transaction details.
- The business metric used is Reducing the total credit risk value.
- The goal to be achieved is to reduce losses due to payment failures by making predictions based on customer history to provide the right decisions and solutions

## Data Analysis
The data analysis process flow consists of:
### EDA (Exploratory Data Analysis)
Insights obtained from EDA results
    
    1. Delinq 2 Years by Term
 
![Total kenakalan terhadap tenor](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/0a228cd2-2e04-40bb-b4d0-493247783373)


    2. High Risk Goals
![Tujuan pinjaman yang memiliki resiko tinggi](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/47713c6f-83aa-4d48-b579-3253b73162d2)


    3. Comparison of Annual Income & Delinq 2 years based on region

![Perbandingan Annual Income   Delinq 2 Years ](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/38e296d5-6b0e-4f91-86a4-3895ba75c812)

    4. Delinq by Country
![Delinq by Country](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/9e09cda7-38e2-4370-83f1-5991da469f3a)


    5. Revolving Balance vs Revolving Utilization by Earliest Cr Line
![RB vs RU ](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/a8134f87-4272-4be9-a25e-b83293e21c7f)


### Summary
After the EDA was carried out, the main cause of bad credit was customers who borrowed to build a small business, the term of interest was 36 months.
In a way, this is the trigger that causes bad credit because building a business has a higher risk because experience in financial management is not yet strong, coupled with very tight market competition, this means that small businesses must have sufficient financial foundations to face existing competitors. Using a term of 36 months instead of 60 months can also be quite a strong trigger due to the difference in interest rates that have to be paid by different customers.
Countries that have a high level of delinquency are in the eastern states. It is necessary to analyze further why the eastern states have had more delinquencies in the last 2 years, but on the other hand, revolving openings in the eastern states are greater in other states.

















## Features

In data processing, several stages are carried out, namely: 
1. Ferature enginering

    Handle missing value and type data

        data.dropna(axis=1, how='all')
        
        def impute_with_mode(data, columns): 
        for column in columns:
            mode = data[column].mode()[0]
            data[column].fillna(mode, inplace=True)

        def impute_with_median(data, columns):
            for column in columns:
            median = data[column].median()
            data[column].fillna(median, inplace=True)
        def impute_with_mean(data, columns):
            for column in columns:
            mean = data[column].mean()
            data[column].fillna(mean, inplace=True)

        data['Tenor'] = data['Tenor'].str.replace ('months','')
        data['Tenor'].unique()
        data['Tenor'] =data['Tenor'].astype(int)

2. Feature transform & Standarisasi

    Label Encoding & Standarisasi
        
        from sklearn.preprocessing import StandardScaler
        scaler = StandardScaler()


        cat = [col for col in df.select_dtypes (include='object').columns.tolist()]
        hot = pd.get_dummies(df[cat])
3. Feature Selection

        corrmat = standar_df.corr()
        sns.heatmap(corrmat, cmap='BrBG', annot=True, vmin= 0.7)



## Deployment

From the analysis results, after comparing several algorithms, the XGBoost model is the best model in this case.




## Model Validation
At this stage, I evaluated the model using two methods with the XGBoost algorithm:

### 1. Hold out 
 Confusion Matrik
    
    [[8674 1331]
     [2061 8102]]

               precision    recall  f1-score   support

            0       0.81      0.87      0.84     10005
            1       0.86      0.80      0.83     10163

    accuracy                            0.83     20168
    macro avg       0.83      0.83      0.83     20168
    weighted avg    0.83      0.83      0.83     20168
### 2. K-Fold

Confusion Matrik

    Confusion Matrik
    [[44587    41    64]
    [ 2251  42536    52]
    [    1     3  44620]]
----------------------------------------------------------------------------
               precision    recall  f1-score   support

            0       0.95      1.00      0.97     44692
            1       1.00      0.95      0.97     44839
            2       1.00      1.00      1.00     44624

    accuracy                            0.98    134155
    macro avg       0.98      0.98      0.98    134155
    weighted avg    0.98      0.98      0.98    134155

After conducting numerous experiments, it was discovered that utilizing the XGBoost model with K-Fold cross-validation resulted in a greater reduction in bad debts. The improvement compared to not using the model exceeded 45%.

![Capture](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/651feaaf-e3f6-4fff-a6b1-dcff29deeb20)

## Bussines Recommendation

- Providing special loan or credit services for small businesses.
- Develop fintech solutions or applications that utilize credit data to provide services such as personal money management, investment portfolio processing.
- Developing a peer to peer lending platform that uses credit data analysis to match borrowers with lenders to evaluate loan credit risk.
## 🔗 Links
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/)



## 🛠 Skills
PostgreSQL, Python, Tableau, Git, R, C++ , Oracle, Dbeaver, and Microsoft Office.


