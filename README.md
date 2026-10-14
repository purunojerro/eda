import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Create a sample dataset
data = {
    "Name": ["Arun", "Bala", "Charan", "Divya", "Ezhil"],
    "Age": [20, 21, 19, 22, 20],
    "Marks": [85, 90, 78, 95, 88]
}

df = pd.DataFrame(data)

# Display the dataset
print("Dataset:")
print(df)

# Display first five rows
print("\nFirst 5 Rows:")
print(df.head())

# Dataset shape
print("\nDataset Shape:")
print(df.shape)

# Dataset information
print("\nDataset Information:")
df.info()

# Statistical summary
print("\nStatistical Summary:")
print(df.describe())

# Check missing values
print("\nMissing Values:")
print(df.isnull().sum())

# Check duplicate rows
print("\nDuplicate Rows:")
print(df.duplicated().sum())

# Histogram
df[["Age", "Marks"]].hist(figsize=(8, 4))
plt.tight_layout()
plt.show()

# Correlation heatmap
plt.figure(figsize=(5, 4))
sns.heatmap(
    df[["Age", "Marks"]].corr(),
    annot=True,
    cmap="coolwarm"
)
plt.title("Correlation Heatmap")
plt.tight_layout()
plt.show()
