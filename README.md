![Monthly Sales Chart](screenshots/monthly_sales_chart.png

# 🛒 Retail Sales Data Analysis (Internship Task 5)

## 🎯 Objective
To analyze a retail sales dataset using *Pandas* and *Matplotlib* in *Google Colab*, and extract insights such as:
- Monthly sales trends
- Product-wise sales
- Gender-wise revenue split  
with *visualizations* and proper *data cleaning*.

---

## 🧰 Tools & Technologies
- *Python* (Pandas, Matplotlib)
- *Google Colab*
- *CSV file* (hosted on GitHub)

---

## 📁 Dataset Description
The dataset used is a retail transaction dataset containing:
- Transaction ID: Unique sale ID  
- Date: Date of purchase  
- Customer ID: ID of the buyer  
- Gender: Gender of the buyer  
- Age: Age of the customer  
- Product Category: Item category  
- Quantity: Number of items purchased  
- Price per Unit: Price of a single item  
- Total Amount: Final billed amount (Quantity × Price per Unit)

---

## 🔎 Key Tasks Performed

### ✅ Step 1: Importing Required Libraries
```python
import pandas as pd
import matplotlib.pyplot as plt

> pandas is used for data manipulation, and matplotlib for visualizations.




---

✅ Step 2: Load the Dataset from GitHub

url = "https://raw.githubusercontent.com/LegendSeyi/Retail-Data-Analysis/main/retail_sales_dataset.csv"
data = pd.read_csv(url)

> The dataset is loaded directly into a Pandas DataFrame using the raw GitHub link.




---

✅ Step 3: Clean Column Names

data.columns = data.columns.str.strip()

> This removes unwanted spaces in column headers, which helps prevent KeyErrors later.




---

✅ Step 4: Convert Date Column to Datetime Format

data['Date'] = pd.to_datetime(data['Date'])

> Allows easy extraction of month and sorting based on time.




---

✅ Step 5: Extract Month

data['Month'] = data['Date'].dt.month

> Adds a new Month column to analyze month-wise sales.




---

✅ Step 6: Analyze Monthly Sales

monthly_sales = data.groupby('Month')['Total Amount'].sum()

> Groups sales data by month and calculates total sales in each month.




---

✅ Step 7: Analyze Sales by Product Category

category_sales = data.groupby('Product Category')['Total Amount'].sum().sort_values(ascending=False)

> Finds out which product category brings in the most revenue.




---

✅ Step 8: Analyze Sales by Gender

gender_sales = data.groupby('Gender')['Total Amount'].sum()

> Understands the sales distribution between Male and Female customers.




---

✅ Step 9: Visualize the Data

📊 Monthly Sales Bar Chart

monthly_sales.plot(kind='bar', color='skyblue')

📦 Product Category Sales Bar Chart

category_sales.plot(kind='bar', color='lightgreen')

🚻 Gender-wise Sales Pie Chart

gender_sales.plot(kind='pie', autopct='%1.1f%%')

> These visualizations help interpret the trends more intuitively.




---

📈 Visual Output (See /screenshots/ Folder)

Visualization	File Name

Dataset Preview	preview.png
Printed Column Names	column_names.png
Monthly Sales Output	monthly_sales_output.png
Product Category Sales Output	category_sales_output.png
Gender Sales Output	gender_sales_output.png
Monthly Sales Bar Chart	monthly_sales_chart.png
Product Category Bar Chart	category_sales_chart.png
Gender Pie Chart	gender_sales_chart.png



---

🧠 Concepts Used

Concept	Used in Code

read_csv()	Load dataset
str.strip()	Clean headers
to_datetime()	Convert Date
groupby() + sum()	Aggregations
plot(kind='bar')	Bar Charts
plot(kind='pie')	Pie Chart
sort_values()	Sorting results



---

📂 Project Folder Structure

task5-retail-data-analysis/
│
├── retail_sales_analysis.ipynb       # ✅ Final Google Colab notebook
├── README.md                         # ✅ Full documentation
├── screenshots/                      # ✅ All required visual outputs
│   ├── preview.png
│   ├── column_names.png
│   ├── monthly_sales_output.png
│   ├── category_sales_output.png
│   ├── gender_sales_output.png
│   ├── monthly_sales_chart.png
│   ├── category_sales_chart.png
│   └── gender_sales_chart.png


---

🚀 How to Run the Code

1. Open Google Colab


2. Upload the retail_sales_analysis.ipynb


3. Press Runtime → Run all


4. Observe printed insights and generated charts


5. Save as PDF or take screenshots for documentation




---

🧑‍💼 Submitted by: Rohith K N

Python Intern @ [Company/Program Name]

Data Analysis Enthusiast | Web Developer

🔗 GitHub: https://github.com/Rohith-a441



---
