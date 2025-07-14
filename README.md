# Water Quality Analysis

## Project Overview

This project involves an Exploratory Data Analysis (EDA) of the California Department of Water Resources water sample dataset, focusing on chemical and physical parameters of water sources across California. The primary goal was to analyze key attributes, such as the 'parameter' (measured constituent) and 'result' (measured value), with a specific focus on pH levels in relation to sample depth. The analysis was conducted using Python, leveraging libraries like Pandas, NumPy, Matplotlib, Seaborn, and SciPy for data processing, statistical analysis, and visualization.

## Dataset

The dataset, sourced from the California Department of Water Resources, contains current and historical data on water quality parameters across various counties. This project analyzed a subset of 500,000 records from the `CAWaterQualityLabResults.csv` file, focusing on:
- **Key Attributes**:
  - `parameter`: The constituent measured (e.g., pH, Conductance, Dissolved Boron).
  - `result`: The measured value of the constituent.
  - `sample_depth`: Depth at which the sample was collected.
  - Other attributes include `station_id`, `station_type`, `latitude`, `longitude`, and `county_name`.
- **Scope**: The analysis focused on pH levels in Alameda County groundwater samples, comparing pH distributions at maximum and minimum sample depths.

### Preprocessing
- Loaded a subset of 500,000 rows to manage computational resources.
- Removed rows with missing values in `sample_depth` and `result` to ensure data integrity.
- Converted `result` to numeric format, handling non-numeric values by coercion to NaN, and dropped remaining NaN values.
- Final dataset size: 187,326 records after cleaning.
- Analyzed pH data by splitting into maximum and minimum sample depth groups for comparison.

## Analysis

The EDA included the following steps:
1. **Data Exploration**:
   - Examined dataset structure, identifying 18 columns with a mix of numeric (e.g., `result`, `sample_depth`) and categorical (e.g., `parameter`, `county_name`) data types.
   - Identified missing values in `sample_depth` (29%), `result` (1.1%), and other columns, addressed through targeted cleaning.
2. **Statistical Analysis**:
   - Calculated descriptive statistics (e.g., mean pH for maximum depth: 7.896, minimum depth: 8.03).
   - Performed a two-sample t-test to compare pH levels at maximum and minimum depths, yielding a p-value of 0.0483 (below alpha = 0.05), suggesting no significant difference in pH due to sample depth.
3. **Visualizations**:
   - Generated kernel density estimation (KDE) plots using Seaborn to visualize pH distributions for maximum and minimum sample depths.
   - Used Matplotlib for plotting to inspect data distributions and relationships.

## Key Findings

- **pH Analysis**: The t-test indicated no significant difference in pH levels between maximum and minimum sample depths in Alameda County groundwater (p-value = 0.0483), suggesting sample depth does not strongly influence pH acidity.
- **Data Quality**: Missing values in `sample_depth` and `result` required careful cleaning to ensure reliable analysis.
- **Dataset Insight**: The dataset's extensive variables provide a robust foundation for water quality analysis, with potential for broader geographic and parameter-based studies.

## Installation

To run this project, ensure you have the following dependencies installed:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

Download the `CAWaterQualityLabResults.csv` dataset from the California Department of Water Resources and place it in the `data/` directory.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/water-quality-analysis.git
   cd water-quality-analysis
   ```

2. Set up the dataset:
   - Place `CAWaterQualityLabResults.csv` in the `data/` directory.

3. Run the Jupyter Notebook:
   ```bash
   jupyter notebook Water_Quality_Analysis.ipynb
   ```

4. Follow the notebook to explore the data, perform statistical analysis, and generate visualizations.

## Next Steps

- **Expand Geographic Scope**: Analyze pH levels across other California counties to identify regional variations.
- **Filter by Water Type**: Differentiate between groundwater and surface water to assess pH variations by water source.
- **Advanced Analysis**: Incorporate additional parameters (e.g., Conductance, Dissolved Chloride) and explore correlations using multivariate techniques or machine learning models.
