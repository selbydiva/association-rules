# Association Rules 

Association Rules are if/then statements that identify the relationships or dependencies between the data. The association rule has two parts: antecedent or if and consequent or then. The antecedent is the first part available in data, while the resulting is the resultant part available in combination with the antecedent. (Source : https://www.analyticsvidhya.com/blog/2023/11/what-are-association-rules-in-data-mining/)

In short, Association Rules facilitate the discovery of relationships where item A appearing in conjunction with item B is analyzed using these metrics :

![Slide1](https://github.com/selbydiva/association-rules/assets/154320650/f78599b7-763e-47bf-aef2-6c41369a9da4)

Support measures the frequency with which an itemset appears in the data

Confidence measures the likelihood of occurrence item B and item A simultaneously in the data

Lift measures how much more likely item B is to be purchased when item A is purchased, compared to the likelihood of purchasing item B independently

# Association Rules (Shop Store)

A large shopping center wants to rearrange the positions of all its stores. The new arrangement should consider the relationships between stores, where stores are deemed related if customers make purchases at both on the same day. The more closely related two stores are, the closer they should be positioned. To achieve this, the shopping center has a daily dataset of historical transactions from last month. Dataset used in this project is Shop Store Data. The dataset under consideration pertains to a retail shop store, capturing key transactional information. The data is structured around three main attributes: date, cust_no, and merchant_nm.

date: This attribute records the specific date on which each transaction took place. It allows for the analysis of purchasing patterns over time, enabling insights into trends, seasonality, and peak shopping periods.

cust_no: This attribute identifies the customers who have made purchases. Analyzing this data can provide valuable information about customer behavior, preferences, and demographics, which can be leveraged to enhance customer satisfaction and loyalty.

merchant_nm : This attribute specifies the particular shop where the purchase was made. It helps in understanding the performance of different store locations, identifying high-performing stores, and those that may need strategic improvements.

Here is what the bottom 5 data looks like

![Slide2](https://github.com/selbydiva/association-rules/assets/154320650/a0119b08-bd1b-4c8e-b867-15c6e6ff18ec)

To expedite the process, we can use tools to implement Association Rules on this data. In Python, we can use the mlxtend library to apply Association Rules and pyvis to visualize the results.

Since this project focus on the relation between stores so the selected rules are top 10 rules based on confidence value. By focusing on confidence levels without considering whether the support is high or low, we can better understand the relationships within each rule. The expectation is that support can be improved by bringing two related stores closer together if the support value is low, and support can be maintained if the value is already high. Here is the result :

![Slide3](https://github.com/selbydiva/association-rules/assets/154320650/2ad32a3d-eca6-4032-8591-d076c62690c7)


To understand that table, let's take a look on first row of that table. It's Mango -> H&M, it means people who make purchase at Mango also make purcahse at H&M


- In Association Rules, Mango is Antecedents and H&M Consequents Support so Antecedents Support and Consequents Support are support values for each store.
- Support measures the frequency with which Mango and H&M appears simultaneously in the data. So, appearance of Mango and H&M simultaneously is 0.2%
- Confidence measures the likelihood of occurrence H&M and Mango simultaneously in the data. So, 23,5% of those who makes purchase in Mango, makes purchase in H&M as well.
- By looking at confidence value

