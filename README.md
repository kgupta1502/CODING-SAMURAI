# CODING-SAMURAI
# STEP 1 : This Step involves Loading and Examining of Data

import pandas as pd
# Load the dataset
df = pd.read_csv('/content/drive/MyDrive/listings.csv')

# Take a look at the first few rows of the dataset
print(df.head())

# Get an overview of the dataset's structure and summary statistics
print(df.info())
print(df.describe())


# STEP 2 : Now Moving on to the Next Part, We have to Clean the data that includes Handling of missing values and cleaning the data. This may involve filling missing values, removing duplicates, or correcting data inconsistencies.

import pandas as pd
# Load the dataset
df = pd.read_csv('/content/drive/MyDrive/listings.csv')

# Check for missing values
print(df.isnull().sum())

# Drop rows with missing values
df = df.dropna()
# Checking data types of each column
print(df.dtypes)

#Handling the outliers
print(df.describe())

# Clip values in a column to a specific range
df['price'] = df['price'].clip(lower=0, upper=1000)

# Removing the Duplicates
print(df.duplicated().sum())

# Now summing up all the code, we get the following updated code
import pandas as pd

# Load the dataset
df = pd.read_csv('/content/drive/MyDrive/listings.csv')

# Check for missing values
print(df.isnull().sum())

# Drop rows with missing values
df = df.dropna()

# Check data types
print(df.dtypes)

# Check for outliers
print(df.describe())

# Clip values in a column to a specific range
df['price'] = df['price'].clip(lower=0, upper=1000)

# Check for duplicates
print(df.duplicated().sum())

# Remove duplicate rows
df = df.drop_duplicates()

import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('/content/drive/MyDrive/listings.csv')

# Calculate the average price of listings
avg_price = df['price'].mean()
print(f"Average price of listings: ${avg_price:.2f}")

# Check if the 'property_type' column exists in the dataframe
if 'property_type' in df.columns:
    # Get the count of each property type
    property_types = df['property_type'].value_counts()
    print("Property types and their counts:")
    print(property_types)

    # Plot a bar chart
    plt.figure(figsize=(10, 6))
    property_types.plot(kind='bar')
    plt.title('Distribution of Property Types')
    plt.xlabel('Property Type')
    plt.ylabel('Count')
    plt.show()
else:
    print("The 'property_type' column does not exist in the dataframe.")

# Check if the 'neighborhood' column exists in the dataframe
if 'neighborhood' in df.columns:
    # Get the count of each neighborhood
    neighborhoods = df['neighborhood'].value_counts()
    print("Neighborhoods and their counts:")
    print(neighborhoods)

    # Plot a bar chart
    plt.figure(figsize=(10, 6))
    neighborhoods.plot(kind='bar')
    plt.title('Distribution of Neighborhoods')
    plt.xlabel('Neighborhood')
    plt.ylabel('Count')
    plt.show()
else:
    print("The 'neighborhood' column does not exist in the dataframe.")

# Plot a histogram of prices
plt.figure(figsize=(10, 6))
df['price'].plot(kind='hist', bins=50)
plt.title('Histogram of Prices')
plt.xlabel('Price')
plt.ylabel('Frequency')
plt.show()

# Check if the 'property_type' column exists in the dataframe
if 'property_type' in df.columns:
    # Plot a box plot of prices by property type
    plt.figure(figsize=(10, 6))
    df.boxplot(column='price', by='property_type')
    plt.title('Box Plot of Prices by Property Type')
    plt.xlabel('Property Type')
    plt.ylabel('Price')
    plt.show()
else:
    print("The 'property_type' column does not exist in the dataframe.")

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
df = pd.read_csv('/content/drive/MyDrive/listings.csv')

# Check if the 'price' column exists in the dataframe
if 'price' in df.columns:
    # Plot a histogram of prices
    plt.figure(figsize=(10, 6))
    df['price'].plot(kind='hist', bins=50)
    plt.title('Histogram of Prices')
    plt.xlabel('Price')
    plt.ylabel('Frequency')
    plt.show()
else:
    print("The 'price' column does not exist in the dataframe.")

# Check if the 'room_type' column exists in the dataframe
if 'room_type' in df.columns:
    # Plot a bar chart of room types
    plt.figure(figsize=(10, 6))
    df['room_type'].value_counts().plot(kind='bar')
    plt.title('Distribution of Room Types')
    plt.xlabel('Room Type')
    plt.ylabel('Count')
    plt.show()
else:
    print("The 'room_type' column does not exist in the dataframe.")

# Check if the 'neighborhood' column exists in the dataframe
if 'neighborhood' in df.columns:
    # Plot a bar chart of neighborhoods
    plt.figure(figsize=(10, 6))
    df['neighborhood'].value_counts().plot(kind='bar')
    plt.title('Distribution of Neighborhoods')
    plt.xlabel('Neighborhood')
    plt.ylabel('Count')
    plt.show()
else:
    print("The 'neighborhood' column does not exist in the dataframe.")

# Check if the 'number_of_reviews' column exists in the dataframe
if 'number_of_reviews' in df.columns:
    # Plot a scatter plot of price vs. number of reviews
    plt.figure(figsize=(10, 6))
    plt.scatter(df['price'], df['number_of_reviews'])
    plt.title('Price vs. Number of Reviews')
    plt.xlabel('Price')
    plt.ylabel('Number of Reviews')
    plt.show()
else:
    print("The 'number_of_reviews' column does not exist in the dataframe.")

# Check if the 'neighborhood' and 'price' columns exist in the dataframe
if 'neighborhood' in df.columns and 'price' in df.columns:
    # Plot a box plot of price by neighborhood
    plt.figure(figsize=(10, 6))
    sns.boxplot(x='neighborhood', y='price', data=df)
    plt.title('Box Plot of Price by Neighborhood')
    plt.xlabel('Neighborhood')
    plt.ylabel('Price')
    plt.show()
else:
    print("The 'neighborhood' or 'price' column does not exist in the dataframe.")

# Check if the dataframe is not empty and has at least two columns
if not df.empty and len(df.columns) >= 2:
    # Select only numerical columns
    numerical_cols = df.select_dtypes(include=[int, float]).columns

    # Check if there are at least two numerical columns
    if len(numerical_cols) >= 2:
        # Plot a heatmap of correlations
        plt.figure(figsize=(10, 6))
        sns.heatmap(df[numerical_cols].corr(), annot=True, cmap='coolwarm')
        plt.title('Heatmap of Correlations')
        plt.show()
    else:
        print("The dataframe must contain at least two numerical columns to plot the heatmap of correlations.")
else:
    print("The dataframe is empty or has less than two columns.")

# Check if the 'property_type' column exists in the dataframe
if 'property_type' in df.columns:
    # Plot a bar chart of property types
    plt.figure(figsize=(10, 6))
    df['property_type'].value_counts().plot(kind='bar')
    plt.title('Distribution of Property Types')
    plt.xlabel('Property Type')
    plt.ylabel('Count')
    plt.show()
else:
    print("The 'property_type' column does not exist in the dataframe.")

# Check if the 'inimum_nights' column exists in the dataframe
if 'inimum_nights' in df.columns:
    # Plot a scatter plot of price vs. minimum nights
    plt.figure(figsize=(10, 6))
    plt.scatter(df['price'], df['minimum_nights'])
    plt.title('Price vs. Minimum Nights')
    plt.xlabel('Price')
    plt.ylabel('Minimum Nights')
    plt.show()
else:
    print("The 'inimum_nights' column does not exist in the dataframe.")

# Check if the 'room_type' and 'price' columns exist in the dataframe
if 'room_type' in df.columns and 'price' in df.columns:
    # Plot a violin plot of price by room type
    plt.figure(figsize=(10, 6))
    sns.violinplot(x='room_type', y='price', data=df)
    plt.title('Violin Plot of Price by Room Type')
    plt.xlabel('Room Type')
    plt.ylabel('Price')
    plt.show()
else:
    print("The 'room_type' or 'price' column does not exist in the dataframe.")

# Import necessary libraries
import folium
import pandas as pd

# Load the dataset
df = pd.read_csv('/content/drive/MyDrive/listings.csv')

# Create a map
m = folium.Map(location=[40, -74], zoom_start=12)

# Add markers to the map
for index, row in df.iterrows():
    lat = row['latitude']
    lon = row['longitude']
    name = row['name']
    price = row['price']
    folium.Marker([lat, lon], popup=f"{name} - ${price}").add_to(m)

# Save the map as an HTML file
m.save('airbnb_listings_map.html')

# Create a map
m = folium.Map(location=[40, -74], zoom_start=12)

# Add CircleMarkers to the map
for index, row in df.iterrows():
    lat = row['latitude']
    lon = row['longitude']
    folium.CircleMarker([lat, lon], radius=10, color='blue', fill=True).add_to(m)

# Save the map as an HTML file
m.save('airbnb_listings_density_map.html')

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load your dataset into a pandas DataFrame
df = pd.read_csv('/content/drive/MyDrive/listings.csv')

# Select only numeric columns to calculate correlation
numeric_cols = df.select_dtypes(include=['int64', 'float64']).columns
corr_matrix = df[numeric_cols].corr()

# Visualize the correlation matrix using a heatmap
plt.figure(figsize=(10, 8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', square=True)
plt.title('Correlation Matrix')
plt.show()

