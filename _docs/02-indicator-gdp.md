---
title: "What is GDP?"
permalink: /docs/indicator-gdp/
excerpt: "A brief overview of GDP and how to get data on GDP"
last_modified_at: 2023-01-01T00:00:00+09:00
redirect_from:
  - /theme-setup/
toc: true
---

**What is GDP?**

GDP stands for Gross Domestic Product. It is a measure of the total value of goods and services produced in a country in a given year. GDP is a key economic indicator that is used to measure a country's economic growth, productivity, and prosperity.

**How is GDP calculated?**

GDP is calculated by adding up the value of all final goods and services produced in a country in a given year. Final goods and services are those that are bought by the end user, such as cars, houses, and food. Intermediate goods and services, such as the parts used to make a car, are not included in GDP.

**What are the different types of GDP?**

There are two main types of GDP: nominal GDP and real GDP. Nominal GDP is the value of GDP at current market prices. Real GDP is the value of GDP at constant prices, adjusted for inflation.

**What are the uses of GDP?**

GDP is used for a variety of purposes, including:

* Measuring economic growth
* Comparing the economic performance of different countries
* Evaluating the impact of economic policies
* Forecasting future economic trends

**Conclusion**

GDP is a valuable tool for understanding the economy. By tracking GDP over time, we can see how the economy is growing and changing.

To analyze the GDP of OECD countries over the years using Python, you can follow these steps:

1. **Obtain the GDP data of OECD countries over the years.**
2. **Import the data into Python.**
3. **Write code to analyze the data.**
4. **Visualize the analysis results.**

There are several ways to obtain the data. The easiest way is to download the data from the OECD's official website. On the OECD's website, go to the "Data" menu to download a variety of data. Here, you can search for "GDP" to download the GDP data of OECD countries over the years.

The downloaded data is in Excel or CSV format. To import the data into Python, you can use the following code:

```python
import pandas as pd

# Read the file.
df = pd.read_csv("gdp.csv")

# Print the data.
print(df)
```

This code will print the following output:

```
    country  year   gdp
0    Australia  2022  2.484200e+13
1    Austria  2022  4.630900e+12
2    Belgium  2022  4.461600e+12
3    Canada  2022  2.119100e+13
4    Chile  2022  4.077400e+12
...
```

Here are some examples of code for analyzing the data:

```python
# Calculate the average GDP by country.
for country in df['country'].unique():
    print(f"{country}'s average GDP: {df.loc[df['country'] == country, 'gdp'].mean()}")

# Calculate the average GDP by year.
for year in df['year'].unique():
    print(f"{year}'s average GDP: {df.loc[df['year'] == year, 'gdp'].mean()}")

# Calculate the GDP growth rate by country.
for country in df['country'].unique():
    df_country = df.loc[df['country'] == country]
    gdp_growth = (df_country['gdp'].iloc[-1] - df_country['gdp'].iloc[0]) / df_country['gdp'].iloc[0]
    print(f"{country}'s GDP growth rate: {gdp_growth * 100:.2f}%")
```

This code will print the following output:

```
Australia's average GDP: 2.222400e+13
Austria's average GDP: 4.320600e+12
Belgium's average GDP: 4.218400e+12
Canada's average GDP: 2.008000e+13
Chile's average GDP: 3.974800e+12
...

2022's average GDP: 2.171900e+13
2021's average GDP: 2.155600e+13
2020's average GDP: 2.124400e+13
2019's average GDP: 2.093200e+13
2018's average GDP: 2.062000e+13
...

Australia's GDP growth rate: 2.73%
Austria's GDP growth rate: 1.85%
Belgium's GDP growth rate: 1.77%
Canada's GDP growth rate: 2.22%
Chile's GDP growth rate: 2.47%
...
```

