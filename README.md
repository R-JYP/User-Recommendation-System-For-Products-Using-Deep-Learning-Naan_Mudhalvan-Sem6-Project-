# User-Recommendation-System-For-Products-Using-Deep-Learning-Naan_Mudhalvan-Sem6-Project-
Problem Statement
In the rapidly evolving landscape of e-commerce, personalized recommendations play a 
pivotal role in enhancing user experience and boosting sales. Our company, XYZ Retail, 
aims to leverage deep learning techniques to develop an advanced recommendation 
system based on historical sales data. The goal is to provide personalized product 
suggestions to users, ultimately increasing customer satisfaction and driving revenue.


Objective:
The objective of this project is to design and implement a deep learning-based 
recommendation system that can analyze past sales data and generate accurate product 
recommendations for individual users. The system should be capable of understanding 
user preferences, identifying patterns, and suggesting items that align with the user's 
interests.

Dataset used : sample_sales_data.csv

Code for generating the dataset using faker library to generate random names and 
words for users and items, respectively.
Step 1 : pip install faker
Step 2 : Run the following code
import pandas as pd
import numpy as np
from faker import Faker
import random
import datetime
fake = Faker()
# Generate sample users
num_users = 100
users = [fake.name() for _ in range(num_users)]
# Generate sample items
num_items = 50
items = [fake.word() for _ in range(num_items)]
# Generate sample sales data
num_transactions = 500
data = {
 'user': [random.choice(users) for _ in range(num_transactions)],
 'item': [random.choice(items) for _ in range(num_transactions)],
 'purchase': [random.choice([0, 1]) for _ in range(num_transactions)],
 'timestamp': [fake.date_time_between(start_date="-1y", end_date="now") for _ in 
range(num_transactions)]
}
sales_data = pd.DataFrame(data)
# Save the generated data to a CSV file
sales_data.to_csv('sample_sales_data.csv', index=False)
# Display the first few rows of the generated data
print(sales_data.head())
