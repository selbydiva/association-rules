# Association Rules (Shop Store)

Association Rules are if/then statements that identify the relationships or dependencies between the data. The association rule has two parts: antecedent or if and consequent or then. The antecedent is the first part available in data, while the resulting is the resultant part available in combination with the antecedent. (Source : https://www.analyticsvidhya.com/blog/2023/11/what-are-association-rules-in-data-mining/)

In short, Association Rules facilitate the discovery of relationships where item A appearing in conjunction with item B is analyzed using these metrics :

![Slide1](https://github.com/selbydiva/association-rules/assets/154320650/f78599b7-763e-47bf-aef2-6c41369a9da4)

Support measures the frequency with which an itemset appears in the data
Confidence measures the likelihood of occurrence item B and item A simultaneously in the data
Lift measures how much more likely item B is to be purchased when item A is purchased, compared to the likelihood of purchasing item B independently


Dataset used in this project is Shop Store Data. The dataset under consideration pertains to a retail shop store, capturing key transactional information. The data is structured around three main attributes: date, cust_no, and merchant_nm.

date: This attribute records the specific date on which each transaction took place. It allows for the analysis of purchasing patterns over time, enabling insights into trends, seasonality, and peak shopping periods.

cust_no: This attribute identifies the customers who have made purchases. Analyzing this data can provide valuable information about customer behavior, preferences, and demographics, which can be leveraged to enhance customer satisfaction and loyalty.

merchant_nm : This attribute specifies the particular shop where the purchase was made. It helps in understanding the performance of different store locations, identifying high-performing stores, and those that may need strategic improvements.

Here is what the bottom 5 data looks like

![Slide2](https://github.com/selbydiva/association-rules/assets/154320650/a0119b08-bd1b-4c8e-b867-15c6e6ff18ec)

To shorten the time, we can use tools for implementing Assotion Rules to this data. In python, we can use library mlxtend to implement Association Rules and pyvis to visualize the result. 

In this process, 10 rules based on top confidence values are taken. By focus on confidence level without consider the support is high or not, we can dig more about the relation for each rule. The expetations is the support can be improved by making these 2 store closer if the support value is low and and the support can be maintained if the support value already high
