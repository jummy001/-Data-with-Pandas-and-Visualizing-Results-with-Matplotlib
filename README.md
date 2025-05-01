# -Data-with-Pandas-and-Visualizing-Results-with-Matplotlib
# Importing necessary libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.datasets import load_iris

# Load the Iris dataset
iris = load_iris()
df = pd.DataFrame(iris.data, columns=iris.feature_names)
df['species'] = iris.target

# Convert target values to species names
species_map = {0: 'setosa', 1: 'versicolor', 2: 'virginica'}
df['species'] = df['species'].map(species_map)

# Task 1: Line Chart (Trends over Time) - Simulated data for example purposes
# We'll simulate a trend of sepal length over time (here we just use index as time)
plt.figure(figsize=(10, 6))
plt.plot(df.index, df['sepal length (cm)'], color='b', label='Sepal Length')
plt.title('Sepal Length Trend Over Time')
plt.xlabel('Time (Index)')
plt.ylabel('Sepal Length (cm)')
plt.legend()
plt.grid(True)
plt.show()

# Task 2: Bar Chart - Average Sepal Length per Species
plt.figure(figsize=(10, 6))
sns.barplot(x='species', y='sepal length (cm)', data=df, palette='viridis')
plt.title('Average Sepal Length per Species')
plt.xlabel('Species')
plt.ylabel('Average Sepal Length (cm)')
plt.show()

# Task 3: Histogram - Distribution of Sepal Width
plt.figure(figsize=(10, 6))
plt.hist(df['sepal width (cm)'], bins=20, color='skyblue', edgecolor='black')
plt.title('Distribution of Sepal Width')
plt.xlabel('Sepal Width (cm)')
plt.ylabel('Frequency')
plt.show()

# Task 4: Scatter Plot - Sepal Length vs Petal Length
plt.figure(figsize=(10, 6))
plt.scatter(df['sepal length (cm)'], df['petal length (cm)'], alpha=0.6, color='orange')
plt.title('Sepal Length vs Petal Length')
plt.xlabel('Sepal Length (cm)')
plt.ylabel('Petal Length (cm)')
plt.show()

Explanation of the Code:
Loading the Dataset:

The Iris dataset is loaded using sklearn.datasets.load_iris(). It is converted into a Pandas DataFrame for easier manipulation.

Line Chart:

I simulate a trend over time by plotting sepal length against the index of the dataset.

plt.plot() is used to create a simple line chart.

Bar Chart:

A bar chart is created using sns.barplot() to show the average sepal length for each species.

Histogram:

The distribution of sepal width is shown using plt.hist().

Scatter Plot:

plt.scatter() is used to show the relationship between sepal length and petal length.

🖼️ Expected Output:
Line Chart: A line plot showing the trend of sepal length over time (or index).

Bar Chart: A bar plot comparing the average sepal length across the three Iris species.

Histogram: A histogram showing the distribution of sepal width.

Scatter Plot: A scatter plot showing the relationship between sepal length and petal length.

These plots will be displayed one by one as you run the code.

