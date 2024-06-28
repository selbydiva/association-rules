# Association Rules 

Association Rules are if/then statements that identify the relationships or dependencies between the data. The association rule has two parts: antecedent or if and consequent or then. The antecedent is the first part available in data, while the resulting is the resultant part available in combination with the antecedent. (Source : https://www.analyticsvidhya.com/blog/2023/11/what-are-association-rules-in-data-mining/)

In short, Association Rules facilitate the discovery of relationships where item X appearing in conjunction with item Y is analyzed using these metrics :

<img width="1438" alt="AR-1" src="https://github.com/selbydiva/association-rules/assets/154320650/902561b6-86f5-49ca-a15f-d30eccd9e354">

Support measures the frequency with which an itemset appears in the data

Confidence measures how often Y appear in transactions that contain X

Lift measures how much more likely item Y is to be purchased when item X is purchased, compared to the likelihood of purchasing item Y independently

# Association Rules (Shop Store)

A large shopping center wants to rearrange the positions of all its stores. The new arrangement should consider the relationships between stores, where stores are deemed related if customers make purchases at both on the same day. The more closely related two stores are, the closer they should be positioned. To achieve this, the shopping center has a daily dataset of historical transactions from last month. Dataset used in this project is Shop Store Data. The dataset under consideration pertains to a retail shop store, capturing key transactional information. The data is structured around three main attributes: date, cust_no, and merchant_nm.

date: This attribute records the specific date on which each transaction took place. It allows for the analysis of purchasing patterns over time, enabling insights into trends, seasonality, and peak shopping periods.

cust_no: This attribute identifies the customers who have made purchases. Analyzing this data can provide valuable information about customer behavior, preferences, and demographics, which can be leveraged to enhance customer satisfaction and loyalty.

merchant_nm : This attribute specifies the particular shop where the purchase was made. It helps in understanding the performance of different store locations, identifying high-performing stores, and those that may need strategic improvements.

Here is what the bottom 5 data looks like

<img width="1440" alt="AR-2" src="https://github.com/selbydiva/association-rules/assets/154320650/fc2c24b1-3061-4fe1-b3dc-9f76f96d161d">

To expedite the process, we can use tools to implement Association Rules on this data. In Python, we can use the mlxtend library to apply Association Rules and pyvis to visualize the results.

Since this project focus on the relation between stores so the selected rules are top 10 rules based on confidence levels. By focusing on confidence levels without considering whether the support is high or low, we can better understand the relationships within each rule. The expectation is that support can be improved by bringing two related stores closer together if the support value is low, and support can be maintained if the value is already high. Here is the result :

<img width="1440" alt="AR-3" src="https://github.com/selbydiva/association-rules/assets/154320650/c89657f7-eadf-43a7-9139-61bbe8460ffe">


To understand the table, let's first examine the first row. It shows Mango -> H&M, which means that people who make purchases at Mango also tend to make purchases at H&M.

- In association rules, Mango is the antecedent and H&M is the consequent. The support values for each store are called antecedent support and consequent support, respectively.
- Support measures the frequency with which both Mango and H&M appear together in the data. In this case, Mango and H&M appear together 0.2% of the time.
- Confidence measures how often H&M appear in transactions that contain Mango. Here, 23.5% of those who purchase at Mango also purchase at H&M.
- Based on the confidence level, we infer that there is a 23.5% probability that someone who purchases at Mango will also purchase at H&M. However, this does not necessarily indicate a direct relationship between the two stores. It could be that H&M is simply very popular, so many people shop there regardless of whether they shop at Mango. Alternatively, people might specifically intend to shop at H&M, with no actual connection to Mango.
To determine if the 23.5% confidence level is meaningful and not just a coincidence, we use the lift metric. By comparing confidence with H&M's support, we can discern whether the high confidence level is due to H&M's popularity or if there is a genuine relationship between Mango and H&M.

A lift value greater than 1 indicates a positive association, meaning that the occurrence of Mango increases the likelihood of H&M occurring.
A lift value equal to 1 indicates no association, meaning that the occurrence of Mango does not affect the likelihood of H&M occurring.  
A lift value less than 1 indicates a negative association, meaning that the occurrence of Mango decreases the likelihood of H&M occurring.

Since the lift value is 4.399, this indicates that Mango and H&M occur together much more frequently than expected, signifying a very strong positive correlation.

# Visualize The Rules

To visualize the rules we can use library pyvis in python. Here is the visualize of the rules

<img width="1439" alt="AR-5" src="https://github.com/selbydiva/association-rules/assets/154320650/c56ee7fa-fb54-491c-b858-72883e050fab">

This is a visualization showcasing the rules for 13 stores, highlighted by their confidence levels.
