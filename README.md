# Netflix-EDA
This toolkit provides a complete exploratory data analysis solution for Netflix user datasets, offering insights into user behavior patterns, subscription preferences, viewing habits, and login patterns. The analysis includes interactive visualizations using Plotly and prepares data for machine learning models to predict user genre preferences.

# Netflix User Data Exploratory Data Analysis (EDA) Toolkit

A comprehensive Python toolkit for analyzing Netflix user behavior data, featuring interactive visualizations and feature importance analysis for genre preference prediction.

## 📊 Overview

## ✨ Features

### 🔍 **Basic Exploratory Data Analysis**
- Dataset shape and structure analysis
- Data type identification
- Missing value detection
- Summary statistics generation
- Feature engineering (age groups, watch time categories)

### 📈 **User Distribution Analysis**
- Age distribution by subscription type
- Subscription type breakdown
- Geographic distribution of users
- Favorite genre popularity
- Watch time distribution patterns

### 🔗 **Relationship Analysis**
- Age vs. watch time correlation
- Genre preferences by age groups
- Watch time patterns by demographics
- Cross-tabulation heatmaps
- Subscription type preferences

### 🕐 **Login Pattern Analysis**
- Days since last login by subscription type
- Login frequency by favorite genre
- Monthly and weekly login trends
- User engagement patterns

### ⏱️ **Watch Time Analysis**
- Watch time distribution by demographics
- Average consumption by age and subscription
- Genre-specific viewing patterns
- Country-based viewing habits

### 🤖 **Feature Importance for Genre Prediction**
- Correlation analysis for each genre
- Feature importance heatmaps
- Data preparation for ML models
- Predictive modeling insights

## 🛠️ Installation

### Prerequisites

```bash
pip install pandas numpy plotly matplotlib seaborn
```

### Required Libraries

```python
import pandas as pd
import numpy as np
import plotly.express as px
import plotly.graph_objects as go
from plotly.subplots import make_subplots
import matplotlib.pyplot as plt
import seaborn as sns
from datetime import datetime
```

## 📁 Data Format

Your Netflix user dataset should be a CSV file with the following columns:

| Column | Type | Description |
|--------|------|-------------|
| `User_ID` | Integer | Unique user identifier |
| `Name` | String | User name |
| `Age` | Integer | User age |
| `Country` | String | User's country |
| `Subscription_Type` | String | Basic/Standard/Premium |
| `Favorite_Genre` | String | User's preferred genre |
| `Watch_Time_Hours` | Float | Total watch time in hours |
| `Last_Login` | String/DateTime | Last login date |

### Example Data Structure:
```csv
User_ID,Name,Age,Country,Subscription_Type,Favorite_Genre,Watch_Time_Hours,Last_Login
1,John Doe,25,USA,Premium,Action,45.2,2024-01-15
2,Jane Smith,32,UK,Standard,Drama,32.1,2024-01-20
```

## 🚀 Usage

### Quick Start

```python
from netflix_eda import run_netflix_eda

# Run complete EDA
netflix_df, figures = run_netflix_eda("your_netflix_data.csv")

# Display key visualizations
figures['correlation_matrix'].show()
figures['distributions']['genre_distribution'].show()
figures['relationships']['age_group_vs_genre'].show()
```

### Individual Function Usage

```python
# Load and prepare data
netflix_df = pd.read_csv("netflix_users.csv")
netflix_df = basic_eda(netflix_df)

# Create specific visualizations
dist_figures = plot_user_distributions(netflix_df)
rel_figures = plot_relationships(netflix_df)
login_figures = plot_login_patterns(netflix_df)

# Analyze feature importance
model_df, importance_figures = analyze_feature_importance(netflix_df)
```

## 📊 Generated Visualizations

### Distribution Analysis
- **Age Distribution**: Histogram with subscription type overlay
- **Subscription Pie Chart**: Distribution of subscription types
- **Country Bar Chart**: User distribution by country
- **Genre Popularity**: Most popular genres
- **Watch Time Histogram**: Viewing patterns by subscription

### Relationship Analysis
- **Age vs Watch Time Scatter**: Correlation with trendlines
- **Age-Genre Heatmap**: Genre preferences by age groups
- **Watch Time-Genre Matrix**: Viewing patterns by content type
- **Country-Genre Distribution**: Geographic content preferences
- **Subscription-Genre Analysis**: Premium vs. content preferences

### Login Pattern Analysis
- **Login Recency Box Plots**: Engagement by subscription type
- **Monthly Login Trends**: Seasonal usage patterns
- **Weekday Analysis**: Weekly viewing habits
- **Genre-based Engagement**: Login frequency by content preference

### Feature Importance
- **Individual Genre Predictors**: Top features for each genre
- **Importance Heatmap**: Cross-genre feature comparison
- **Correlation Matrix**: Numeric variable relationships

## 🎯 Key Functions

### `basic_eda(df)`
Performs fundamental data analysis and feature engineering.

**Returns**: Enhanced DataFrame with derived features

### `plot_user_distributions(df)`
Creates distribution visualizations for user demographics.

**Returns**: Dictionary of Plotly figures

### `plot_relationships(df)`
Analyzes relationships between user attributes.

**Returns**: Dictionary of correlation and cross-tabulation plots

### `plot_login_patterns(df)`
Examines user engagement and login behavior.

**Returns**: Dictionary of temporal analysis figures

### `analyze_feature_importance(df)`
Prepares data for ML and analyzes predictive features.

**Returns**: Processed DataFrame and importance visualizations

### `run_netflix_eda(csv_path)`
Executes complete EDA pipeline.

**Returns**: Tuple of (processed_dataframe, all_figures)

## 📈 Output Examples

The toolkit generates various interactive visualizations:

- **Interactive Scatter Plots** with hover information
- **Heatmaps** showing percentage distributions
- **Box Plots** for distribution analysis
- **Bar Charts** with value annotations
- **Pie Charts** with percentage labels
- **Correlation Matrices** with color coding

## 🔧 Customization

### Color Schemes
```python
# Modify color palettes
color_discrete_sequence=px.colors.qualitative.G10
color_continuous_scale='Viridis'
```

### Plot Templates
```python
# Change plot styling
template='plotly_white'  # or 'plotly_dark', 'simple_white'
```

### Feature Engineering
```python
# Customize age groups
bins = [13, 18, 25, 35, 50, 80]
labels = ['13-18', '19-25', '26-35', '36-50', '51+']
```

## 🔍 Analysis Insights

This toolkit helps answer key business questions:

- **User Engagement**: Which demographics are most active?
- **Content Preferences**: What genres drive subscriptions?
- **Churn Risk**: Who hasn't logged in recently?
- **Market Segmentation**: How do preferences vary by region?
- **Product Strategy**: Which features predict genre preferences?

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Troubleshooting

### Common Issues

**Missing Data**: The toolkit handles missing values and provides summaries
```python
print(df.isnull().sum())
```

**Date Format Issues**: Automatically converts Last_Login to datetime
```python
df['Last_Login'] = pd.to_datetime(df['Last_Login'])
```

**Memory Issues**: For large datasets, consider sampling
```python
df_sample = df.sample(n=10000, random_state=42)
```

## 📞 Support

For questions, issues, or contributions:
- Open an issue on GitHub
- Check the troubleshooting section
- Review the example notebooks

## 🎉 Acknowledgments

- Built with Plotly for interactive visualizations
- Pandas for data manipulation
- Scikit-learn principles for feature importance analysis

---

**Happy Analyzing! 📊✨**
