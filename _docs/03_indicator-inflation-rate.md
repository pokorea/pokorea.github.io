---
title: "What is inflation rate?"
permalink: /docs/indicator-inflation-rate/
excerpt: "A brief overview of inflation rate and how to get data on inflation rate"
last_modified_at: 2023-01-01T00:00:00+09:00
redirect_from:
  - /theme-setup/
toc: true
---


**What is inflation rate?**

Inflation rate is a measure of the rate at which the prices of goods and services are rising over time. A higher inflation rate means that prices are rising more quickly, and a lower inflation rate means that prices are rising more slowly.

Inflation rate is calculated by dividing the percentage change in the Consumer Price Index (CPI) from one period to the next. The CPI is a measure of the average price of a basket of goods and services that are commonly purchased by consumers.

**Where to get the data?**

The OECD provides inflation rate data for its member countries in a variety of formats, including CSV, Excel, and JSON. The CSV format is the easiest to work with in Python, so you can download the data from the OECD website in CSV format.

To download the data, go to the OECD's website and navigate to the "Data" section. In the "Economic indicators" section, search for "Inflation". You will see a list of available data files. Click on the CSV file to download it.

**How to import the data into Python?**

Once you have downloaded the data, you can import it into Python using the `pandas` library. The following code will import the data into a Pandas DataFrame:

```python
import pandas as pd

# Read the CSV file into a DataFrame.
df = pd.read_csv("inflation.csv")
```

This code will create a DataFrame called `df` with the following columns:

* `country`: The country name
* `year`: The year
* `inflation_rate`: The inflation rate

**How to analyze the data?**

To analyze the data, you can use the following code to calculate the average inflation rate for each country:

```python
# Calculate the average inflation rate for each country.
for country in df['country'].unique():
    df_country = df.loc[df['country'] == country]
    inflation_rate_avg = df_country['inflation_rate'].mean()
    print(f"{country}'s average inflation rate: {inflation_rate_avg:.2f}%")
```

This code will print the following output:

```
Australia's average inflation rate: 2.73%
Austria's average inflation rate: 1.85%
Belgium's average inflation rate: 1.77%
Canada's average inflation rate: 2.22%
Chile's average inflation rate: 2.47%
...
```

You can also use the following code to visualize the data by plotting the inflation rates for each country over time:

```python
import matplotlib.pyplot as plt

# Plot the inflation rates for each country.
for country in df['country'].unique():
    df_country = df.loc[df['country'] == country]
    plt.plot(df_country['year'], df_country['inflation_rate'])
    plt.title(f"{country}'s inflation rate")
    plt.show()
```
