# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
DEVELOPED BY : SHALINI K
REGISTER NUMBER : 212222240095
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
# Read the dataset
df = pd.read_csv('coin_Bitcoin.csv')
df.head()
df.info()
df.isnull()
# Calculate the mean for numeric columns
mean_values = df.mean(numeric_only=True)
print("Mean values for each column:")
print(mean_values)
# Convert the 'date' column to datetime format for easy manipulation
df['Date'] = pd.to_datetime(df['Date'])
# Step 3: Set 'Date' column as index for resampling
df.set_index('Date', inplace=True)
# Step 4: Verify data types
print("Data Types:\n", df.dtypes)
# Step 5: Check for missing values
print("Missing Values:\n", df.isnull().sum())
# Create subplots for each metric
metrics = ['Close', 'High', 'Low', 'Open', 'Marketcap']
colors = ['blue', 'green', 'red', 'orange', 'purple']
for i, metric in enumerate(metrics, 1):
    plt.subplot(3, 2, i)
    sns.lineplot(data=monthly_data, x=monthly_data.index, y=metric, color=colors[i-1])
    plt.title(f'Monthly Average {metric}')
    plt.xlabel('Date')
    plt.ylabel(f'Mean {metric}')
    plt.grid(True)
    plt.xticks(rotation=45)  # Rotate the x-axis labels for better readability

plt.tight_layout()  # Adjust spacing to prevent overlap
plt.show()  # Display the plots
```
# OUTPUT:

![image](https://github.com/user-attachments/assets/49674f27-28c9-4c46-9fb7-905c7038e911)


# RESULT:
Thus we have created the python code for plotting the time series of given data.
