import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

data = {
    'City': ['Delhi', 'Mumbai', 'Kolkata', 'Chennai', 'Bangalore', 'Hyderabad', 'Pune', 'Ahmedabad', 'Jaipur', 'Lucknow'],
    'Date': ['2023-01-15', '2023-01-15', '2023-01-15', '2023-01-15', '2023-01-15', '2023-01-15', '2023-01-15', '2023-01-15', '2023-01-15', '2023-01-15'],
    'PM2.5': [180, 120, 90, 110, 100, 115, 95, 105, 125, 130],
    'NO2': [50, 30, 25, 40, 35, 45, 38, 42, 50, 48],
    'SO2': [15, 10, 8, 12, 10, 13, 11, 12, 14, 13]
}

air_quality_df = pd.DataFrame(data)
print(air_quality_df.head())
print(air_quality_df.info())

average_pm25 = air_quality_df['PM2.5'].mean()plt.figure(figsize=(12, 6))
sns.barplot(x='City', y='PM2.5', data=air_quality_df) # Changed 'city' to 'City' for x-axis
plt.title('PM2.5 LEVELS by City')
plt.xlabel('City')
plt.ylabel('PM2.5')
plt.xticks(rotation=90)
plt.show()city_highest_no2 = air_quality_df.loc[air_quality_df['NO2'].idxmax(), 'City']
print("\nCity in highest NO2 level", city_highest_no2)
print("\nAverage pm2 across cities:", average_pm25)
