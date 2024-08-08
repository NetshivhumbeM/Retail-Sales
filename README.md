# Retail-Sales

### Table of Contents

- [Project overview](#project-overview)
- [Data Source](#data-source)
- [Tools Used](#tools-used)
- [Data Cleaning and preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results or Findings](#results-or-findings)
- [Recommendations](#recommendations)
- [References](#references)


### Project overview

This project aims to analyze various aspects of sales and customer behavior to help the organization make more informed decisions. It involves examining sales trends, understanding customer demographics and identifying top selling products. This project also looks at product analysis, sales by gender and age-based purchasing patterns. 

### Data Source

Retail Sales data - The primary dataset used for this  analysis is "Retail_sales_dataset.csv" file, containing detailed information about each sales made by the company between 2023 and 2024 and was made accessible on kaggle.

### Tools Used

- Python(Visual Studio) - Data Cleaning and data analysing
- Power BI - Data Visualization/Reports

### Data Cleaning and preparation

in the initial data preparation stage, we perfomed the following tasks:
1. Data loading and inspection
2. Handling Missing Values
3. Data Cleaning and formatting

### Exploratory Data Analysis

The EDA process involved  exploring the sales data to answer key quetions such as:

- The Total number of custormers?
- Top selling product category?
- Which Year, Month and Day made the most sales?
- Are they any returning customers?
- Average a customer spends?

### Data Analysis

Below is some of the interesting codes we used to be able to answer some of the quetions:

This codes helps us determine the number of customers within an age range.
```Python
data['Age']= data['Age'].astype(int)
def no_customer_age(data,age_max,age_min):
    return ((age_min <= data['Age']) & (data['Age']<= age_max)).sum()

##The code ask the person between which ages does he or she wants to find out the number of custormers within that age
print("Age boundries to determine the number of customers withn those age")
age_min =int(input("Enter the minimum age: "))
age_max =int(input("Enter the maximum age: "))


number_customers =no_customer_age(data,age_max=age_max,age_min=age_min)
print("The number of customers between the age of", age_min,"years and",age_max,"years are",number_customers)
```
The following code helps us identify which month generates most sales.

```python
sales_months = data.groupby('Month name')['Total Amount'].sum().reset_index()
sales_months=sales_months.sort_values(by="Total Amount",
                     axis=0,
                     ascending= False)
sales_months
```
### Results or Findings

The analysis results are summarize as follows:

1. There are no returning customers over this period.
2. There are 20 more female custormers than there are male customers.
3. As a result the organization generated more sales from female customers compared to male which ere $9680 less than female custormers sales.
4. The Top selling product category was Beauty category, which might explain the difference in male and female sales.
5. As we move from 2023 to 2024 the total generated sales shows a strong decrease.
6. The average amount a customer uses is 456.0 whereas the median is 135.0 with the maximum and minimum being 2000 and 25 respectively
7. From the age of 18 to a 41 years old the is 487 customers and total sales of 235k.Compared to the age group of 42 to 64 the maximum in which the were 513 customers and  total sales of  221k. This implies young people are the least attracted to the products sold by this organization compared to old people but young people still generate more compared to the older group.

### Recommendations

Based on the data analysis i would recommend that the organization:

- Invest in marketing an promotions for both the age group(old and younger) but prioritize young age group as the generate more sales and also boost their engagement.
- Focus on exanding and promoting beauty products to capitalize on its popularity.
- implement loyalty programs or rewards to encourage customers to return.
- Conduct a research on hy the has been a huge drop in sales from 2023 to 2024.
- Consider price adjustment to balance the median amount spent by a customer and the average spent by a customer.


### References

1. Learning Python/Text Book




  
- 

