# CFG Project: Sales & Time Series Analysis
# Objective: Explore sales trends, volatility, and long-term growth patterns using Python

# ------------------------------------------------------------
# 1. LOAD AND PREPARE SALES DATA
# ------------------------------------------------------------

# Read sales data from CSV and convert sales column into integers for analysis

with open('sales.csv', 'r') as csv_file:
    spreadsheet = csv.DictReader(csv_file)
    sales_numbers = []
    for item in spreadsheet:
        sales_numbers.append(int(item['sales']))
        
        
# ------------------------------------------------------------
# 2. ANALYSE CUMULATIVE SALES GROWTH
# ------------------------------------------------------------

# Method 1: Using NumPy for efficient cumulative sum calculation
import numpy as np
np.cumsum(sales_numbers)

# Method 2: Manual implementation to demonstrate logic behind cumulative growth

CR = []
current = 0
for i in range(0, len(sales_numbers)):
    current += sales_numbers[i]
    CR.append(current)

print('Cumulative Returns: {}'.format(CR))


# ------------------------------------------------------------
# 3. ANALYSE MONTH-ON-MONTH CHANGES
# ------------------------------------------------------------

# Calculate absolute change between consecutive months to identify fluctuations in sales

change = []

for i in range(1, len(sales_numbers)):
    difference = sales_numbers[i] - sales_numbers[i - 1]
    change.append(difference)

print('Month-on-month change: {}'.format(change))
print('\v')

# Calculate percentage change to better understand relative growth or decline

percentagechange = []

for i in range(1, len(sales_numbers)):
    difference = sales_numbers[i] - sales_numbers[i - 1]
    percentage = round((difference / sales_numbers[i - 1]) * 100, 2)
    percentagechange.append(str(percentage) + "%")


# ------------------------------------------------------------
# 4. ANALYSE LONG-TERM GOLD PRICE TRENDS
# ------------------------------------------------------------

# Load gold price data and extract GBP values for analysis

with open('gold.csv', 'r') as csv_file:
    gold_spreadsheet = csv.DictReader(csv_file)
    GBP_prices = []
    for year in gold_spreadsheet:
        GBP_prices.append(float(year['United Kingdom(GBP)']))
        
# Aggregate monthly data into yearly averages to smooth short-term volatility

GBP_year_avg = []
step = 12

for month in range(0, len(GBP_prices), step):
    GBPavg = round(np.average(GBP_prices[month: month + step]), 2)
    GBP_year_avg.append(GBPavg)
