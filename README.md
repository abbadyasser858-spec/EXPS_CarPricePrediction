# Car Price Prediction with Machine Learning

## Project Overview

This project builds machine learning models to predict car prices based on vehicle features like make, model, year, engine size, horsepower, and other characteristics.

The analysis includes:
- Exploratory data analysis (EDA) of car features
- Data preprocessing and feature engineering
- Training 5 different regression models
- Model evaluation and comparison
- Visualizations of predictions and performance

## Dataset

The car dataset contains information about various vehicles with the following features:
- **Make**: Car manufacturer (e.g., Toyota, Ford, BMW)
- **Model**: Specific car model
- **Year**: Year of manufacture
- **Engine Size**: Engine displacement in liters
- **Horsepower**: Engine power output
- **Fuel Type**: Type of fuel (gasoline, diesel, hybrid, etc.)
- **Body Style**: Type of body (sedan, SUV, coupe, etc.)
- **Transmission**: Transmission type (automatic, manual)
- **Price**: Target variable (car price in dollars)

**Dataset Statistics:**
- Multiple car samples across different makes and years
- Mix of categorical and numerical features
- Price range from affordable to luxury vehicles

## Project Structure

```
EXPS_Task3_Car_Price_Prediction/
├── car_price_prediction.ipynb     # Main Jupyter notebook
├── dataset/                       # Folder for dataset
│   └── cars.csv                  # Car dataset
├── results/                       # Output visualizations
│   ├── 01_data_exploration.png
│   ├── 02_model_comparison.png
│   └── 03_predictions.png
├── README.md                      # This file
├── requirements.txt               # Python dependencies
├── .gitignore                     # Git ignore file
└── LICENSE                        # Project license
```

## Analysis Sections

### 1. Data Loading and Exploration
- Load car dataset
- Check data quality (missing values, duplicates)
- Display dataset statistics
- Understand data characteristics

### 2. Data Visualization
- Price distribution histogram
- Feature correlation analysis
- Identify most important features for price prediction

### 3. Data Preparation
- Handle categorical variables (one-hot encoding)
- Separate features from target variable
- Prepare data for machine learning models

### 4. Train-Test Split and Scaling
- Split data into 80% training and 20% testing
- Scale features using StandardScaler
- Ensure all features have similar ranges

### 5. Model Training
Train 5 different regression models:
- **Linear Regression**: Simple linear relationship
- **Ridge Regression**: Linear model with L2 regularization (prevents overfitting)
- **Lasso Regression**: Linear model with L1 regularization (feature selection)
- **Polynomial Regression**: Captures non-linear patterns (degree 2)
- **K-Nearest Neighbors**: Non-parametric approach using nearest neighbors

### 6. Model Evaluation
Calculate performance metrics for each model:
- **MSE**: Mean Squared Error (average squared prediction error)
- **RMSE**: Root Mean Squared Error (error in dollars)
- **MAE**: Mean Absolute Error (average absolute difference)
- **R²**: Coefficient of determination (0-1, higher is better)

### 7. Model Comparison
- Compare all models on test data
- Identify best performing model
- Visualize performance comparison

### 8. Predictions Analysis
- Show actual vs predicted prices for best model
- Display prediction errors (residuals)
- Analyze where model performs best/worst

## Key Findings

### Model Performance
The analysis trains and compares 5 regression models. Performance varies based on:
- Model complexity
- Feature relationships
- Regularization strength
- Distance metric (for KNN)

### Feature Importance
Key findings about features:
- Some features have strong correlation with price
- Feature interactions matter for predictions
- Categorical features (make, body style) significantly impact price

### Regularization Impact
- Ridge regression prevents overfitting through L2 penalty
- Lasso regression performs feature selection through L1 penalty
- Polynomial features capture non-linear relationships

### Prediction Accuracy
- Model performance varies across price ranges
- Some models better for specific car types
- Ensemble approaches could improve accuracy

## Visualizations

### 1. Data Exploration (01_data_exploration.png)
Two-part visualization:
- **Left**: Histogram showing distribution of car prices
- **Right**: Bar chart of top 10 features most correlated with price

**Interpretation**: Shows price spread and which features matter most

### 2. Model Comparison (02_model_comparison.png)
Two-part comparison chart:
- **Left**: R² scores for all models (higher = better, max = 1.0)
- **Right**: RMSE values for all models (lower = better)
- Red bar = best model, Blue = other models

**Interpretation**: Shows which model predicts prices most accurately

### 3. Predictions Analysis (03_predictions.png)
Two-part visualization of best model:
- **Left**: Scatter plot of actual vs predicted prices
  - Points on diagonal = perfect predictions
  - Points off diagonal = prediction errors
- **Right**: Residual plot (errors vs predictions)
  - Points near zero line = good predictions
  - Spread shows prediction uncertainty

**Interpretation**: Shows how close predictions are to actual prices

## How to Use

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/EXPS_Task3_Car_Price_Prediction.git
cd EXPS_Task3_Car_Price_Prediction
```

2. Create virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

### Running the Analysis

1. Add your car dataset to `dataset/` folder as `cars.csv`
   - Required columns: make, model, year, engine_size, horsepower, fuel_type, body_style, transmission, price

2. Start Jupyter:
```bash
jupyter notebook
```

3. Open `car_price_prediction.ipynb`

4. Run all cells to:
   - Load and explore data
   - Visualize distributions and correlations
   - Train all 5 models
   - Evaluate performance
   - Generate visualizations

### Expected Output

When notebook runs successfully:
- Dataset statistics printed
- Data exploration charts displayed
- 5 models trained and evaluated
- Performance comparison table shown
- 3 PNG files saved to results/ folder
- Best model identified
- Prediction analysis displayed

## Dependencies

See `requirements.txt` for complete list. Main packages:
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computing
- **scikit-learn**: Machine learning algorithms
- **matplotlib**: Data visualization
- **seaborn**: Statistical data visualization
- **jupyter**: Interactive notebooks

## Model Explanations

### Linear Regression
- Finds best-fit line through data
- Simple and interpretable
- Assumes linear relationship between features and price

### Ridge Regression
- Linear model with L2 regularization
- Adds penalty to large coefficients
- Reduces overfitting
- Works well when many features are important

### Lasso Regression
- Linear model with L1 regularization
- Can set unimportant coefficients to zero
- Performs feature selection
- Works well when few features are important

### Polynomial Regression
- Uses polynomial features (degree 2)
- Creates interaction terms between features
- Captures curved relationships
- More flexible than linear models

### K-Nearest Neighbors
- Non-parametric regression method
- Predicts based on k=5 nearest neighbors
- No training phase, uses entire dataset
- Works well for complex non-linear patterns

## Conclusions

This car price prediction analysis demonstrates:

1. **Multiple Approaches**: Different models capture patterns differently
2. **Data Preparation Matters**: Feature engineering and scaling are crucial
3. **Model Selection**: Some models significantly outperform others
4. **Regularization Helps**: Ridge and Lasso reduce overfitting
5. **Non-linear Patterns**: Polynomial and KNN capture relationships linear models miss
6. **Real-world Application**: ML can accurately predict prices from car features

## Practical Applications

This type of analysis can be used for:
- **Pricing Optimization**: Setting competitive car prices
- **Valuation**: Estimating used car values
- **Market Analysis**: Understanding price drivers
- **Recommendation Systems**: Suggesting prices to buyers/sellers
- **Fraud Detection**: Identifying unusual price listings

## Internship Requirements Met

✓ Collected car-related features (make, model, year, horsepower, etc.)
✓ Trained regression models to predict car prices
✓ Handled data preprocessing and feature engineering
✓ Used Python libraries (Pandas, Scikit-learn, Matplotlib)
✓ Evaluated model performance with proper metrics
✓ Understood real-world machine learning applications
✓ Created professional visualizations
✓ Complete documentation and explanations

## Author

Created for EXPS Nexus Data Science Internship

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

EXPS Nexus
- Website: www.exps.tech
- Email: hr@expsdz.com
- WhatsApp: +213 551 283 656

## References

- Scikit-learn Documentation: https://scikit-learn.org/
- Pandas Documentation: https://pandas.pydata.org/
- Matplotlib Documentation: https://matplotlib.org/
- Machine Learning Basics: https://en.wikipedia.org/wiki/Machine_learning
- Regression Analysis: https://en.wikipedia.org/wiki/Regression_analysis
