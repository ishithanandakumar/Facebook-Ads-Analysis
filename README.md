# Facebook Ad Sales Analysis

A machine learning project analyzing Facebook ad campaign conversions to predict and optimize ad performance using Naive Bayes and Random Forest classifiers.

## 📊 Project Overview

This project analyzes Facebook ad campaign data to identify key factors that influence conversion rates and build predictive models to classify conversions as Low, Average, or High. The analysis helps optimize ad spending and improve campaign performance.

**Author:**
- Ishitha Nanda Kumar 


## 🎯 Objectives

- Develop predictive models for ad conversion rates
- Identify key factors influencing conversion success
- Compare performance of Naive Bayes vs Random Forest algorithms
- Provide actionable insights for campaign optimization

## 📈 Dataset

- **Source**: Facebook ad campaign data (facebook.csv)
- **Size**: 1,143 rows × 11 columns
- **Features**: age, gender, interest, impressions, clicks, spent, approved_conversion, etc.
- **Target Variable**: Approved_Conversion_Category (Low/Average/High)

### Target Variable Classification:
- **Low**: Approved_Conversion ≤ 2
- **Average**: 2 < Approved_Conversion < 10  
- **High**: Approved_Conversion ≥ 10

## 🛠️ Technologies Used

- **Language**: R
- **Libraries**: 
  - `e1071` (Naive Bayes)
  - `randomForest` (Random Forest)
  - `cluster` (Clustering analysis)
  - `mclust` (Model evaluation)
  - `gplots` & `RColorBrewer` (Visualization)

## 📁 Repository Structure

```
facebook-ad-analysis/
│
├── FacebookAdAnalysis.Rmd          # Main R Markdown analysis file
├── facebook.csv                    # Dataset (add your data file)
├── presentation.pdf                # Project presentation slides
├── README.md                       # This file
└── outputs/                        # Generated plots and results
    ├── histogram_conversions.png
    ├── naive_bayes_cluster.png
    ├── random_forest_cluster.png
    ├── variable_importance.png
    └── heatmap_importance.png
```

## 🚀 Getting Started

### Prerequisites

```r
# Install required packages
install.packages(c("e1071", "randomForest", "cluster", "mclust", 
                   "gplots", "RColorBrewer", "tinytex"))
```

### Running the Analysis

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/facebook-ad-analysis.git
   cd facebook-ad-analysis
   ```

2. **Prepare your data:**
   - Place your `facebook.csv` file in the root directory
   - Ensure the CSV has the required columns: age, gender, interest, impressions, clicks, spent, approved_conversion

3. **Run the analysis:**
   ```r
   # Open and run the R Markdown file
   rmarkdown::render("FacebookAdAnalysis.Rmd")
   ```

## 📊 Methodology

### Data Preprocessing
1. **Data Loading & Exploration**: Load dataset and examine structure
2. **Data Cleaning**: Convert categorical variables to factors
3. **Feature Engineering**: Create conversion categories (Low/Average/High)
4. **Train-Test Split**: 80% training, 20% testing

### Model Development
1. **Naive Bayes Classifier**
   - Probabilistic approach using Bayes' theorem
   - Assumes feature independence

2. **Random Forest Classifier**
   - Ensemble method using multiple decision trees
   - Reduces overfitting through bagging

### Model Evaluation
- **Accuracy Score**: Overall prediction accuracy
- **Confusion Matrix**: Detailed classification performance
- **Adjusted Rand Index (ARI)**: Clustering similarity measure
- **Variable Importance**: Feature impact analysis

## 🎯 Key Findings

### Model Performance
| Model | Accuracy | ARI Score |
|-------|----------|-----------|
| Naive Bayes | 89.08% | 0.496 |
| **Random Forest** | **92.13%** | **0.496** |

### Top 3 Most Important Variables
1. **Impressions** - Number of times ad was displayed
2. **Clicks** - Number of ad clicks received  
3. **Spent** - Amount spent on the campaign

### Conversion Distribution
- **Low conversions**: 88.20% of test data
- **Average conversions**: 10.91% of test data
- **High conversions**: 0.89% of test data

## 💡 Business Insights & Strategy

### Optimization Recommendations:
1. **Focus on High-Impact Variables**: Prioritize optimizing impressions, clicks, and spend allocation
2. **Eliminate Low Performers**: Use model predictions to identify and eliminate underperforming ads
3. **Replication Strategy**: Scale successful campaign features to new campaigns
4. **A/B Testing Framework**: Implement systematic testing for headlines, visuals, and targeting
5. **Real-time Monitoring**: Use model predictions for continuous campaign optimization

## 📈 Visualizations

The analysis includes several key visualizations:
- Conversion distribution histogram
- Naive Bayes cluster plot
- Random Forest cluster plot  
- Variable importance plots
- Feature importance heatmap

## 🔍 Model Selection

**Random Forest was selected as the final model** due to:
- Higher accuracy (92.13% vs 89.08%)
- Better handling of feature interactions
- Robust performance across all conversion categories
- Detailed variable importance insights

## 📝 Usage Example

```r
# Load the trained model
load("facebook_rf_model.RData")

# Predict on new data
new_predictions <- predict(facebook.df.rf, new_data)

# View variable importance
importance(facebook.df.rf)
varImpPlot(facebook.df.rf)
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Create a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.



---

**Note**: This analysis was conducted as part of a data science project at Illinois Institute of Technology. The insights and recommendations are based on the provided dataset and should be validated with additional data before implementation in production environments.
