# Data Preprocessing
The Customer, Product (including Category and Subcategory), Currency, Sales Territory, Geography, and Fact Internet Sales files were used in this analysis. Each file was imported and preprocessed to fit the analysis requirements. The dimension files were merged with the fact file using primary keys.

# Currency Conversion
To accurately compare revenue metrics across different variables, it is essential to report the metrics in the same currency. The data showed that revenue and cost values were reported using different currencies in various countries. To address this, I converted all currencies to USD, which is a globally accepted exchange currency. The [Oando Converter](https://www.oanda.com/currency-converter/en/?from=AUD&to=USD&amount=1) was used for this conversion.

# Features Added
Three new features were added to the fact file:
- **Age Range**: Customer age was calculated by subtracting their Birth Year from 2010 (the maximum year in the dataset), and then categorised into age groups.
- **Yearly Income Level**: The Yearly Income was binned into four categories: Low Income, Lower Middle Income, Upper Middle Income, and High Income.
- **Profit**: This was determined by subtracting Total Product Cost from Sales Amount.

# Techniques Used
Pyspark was employed for the data preprocessing and visualisation stages. At certain points, the Pyspark DataFrame was converted into a pandas DataFrame in order to utilize seaborn and matplotlib for plotting.

# Classification
Logistic regression was applied for classification, using Yearly Income Level as the feature. Logistic regression is efficient for training, simpler to use, and easier to interpret. It does not assume any specific distribution of classes in the feature space and is effective for predicting discrete outcomes.

# Price Prediction
Linear regression was used to predict the company’s profit.

# Insights on Customers
- Female customers earn more on average than male customers.
- Customers categorised as Management earn the highest average income. Male managers earn slightly more than female professionals, which is also seen among other occupational groups like professionals and manual laborers. However, in various other occupations, females generally earn more.
- Customers with graduate and bachelor’s degrees earn more than those without a degree. Interestingly, individuals who partially attended college also earn more than those who did not attend college at all.
- Customers aged 40 to 69 tend to earn more on average, particularly those in the 50–59 age bracket.

# Insights on Profits
- Bikes generated the highest total profit at $10,364,208.01, followed by Accessories at $405,872.47 and Clothing at $124,738.37. Bikes accounted for 95.13% of the total profit.
- Road Bikes had the highest total profit, contributing 44.93% ($4,895,013.31) of the overall profit.
- The United States recorded the highest total profit at $3,900,863.90, which is 518.64% higher than Canada, the lowest at $630,559.52. The United States accounted for 35.80% of the total profit.

# Conclusion
The highest earners among customers are those in management and professional occupations, and these individuals tend to be well-educated. On average, women out-earn men. Professional customers contribute significantly to the company's profits, predominantly purchasing road and mountain bikes, which are the most profitable products. The United States generates the highest profit for the company. The total profit earned by the company during this period is $10,894,818.85. The marketing team can leverage these insights to develop targeted advertisements and messages for the most profitable customer segments. Additionally, the company should investigate the reasons behind the United States’ superior performance compared to other countries.
