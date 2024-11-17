# CardioGoodFitness Market Research Analysis 🏋️‍♂️⌚️

## Project Overview
This repository contains data and analysis for AdRight's market research project on CardioGoodFitness treadmill customers. The research aims to identify typical customer profiles for each treadmill product line by analyzing customer characteristics and purchase patterns from the previous three months of retail store sales.

## Research Objectives
1. Identify the typical customer profile for each treadmill model
2. Investigate differences across product lines with respect to customer characteristics
3. Analyze customer demographics and usage patterns
4. Support data-driven marketing strategies

## Dataset Description

### Data Collection
- **Source**: CardioGoodFitness retail store purchases
- **Time Period**: Three months of sales data
- **Collection Method**: Point of sale and customer surveys
- **Format**: CSV file (CardioGoodFitness.csv)

### Products Under Study
1. **TM195**: Entry-level treadmill
2. **TM498**: Mid-tier treadmill
3. **TM798**: Premium treadmill

### Variables Studied

| Variable          | Description                                        | Type     | Values/Range              |
|------------------|----------------------------------------------------|----------|--------------------------|
| Product          | Treadmill model purchased                          | Nominal  | TM195, TM498, TM798      |
| Gender           | Customer's gender                                  | Nominal  | Male, Female             |
| Age              | Customer's age in years                            | Numeric  | 18-50 years              |
| Education        | Years of education completed                       | Numeric  | 12-21 years              |
| MaritalStatus    | Relationship status                               | Nominal  | Single, Partnered        |
| Income           | Annual household income                            | Numeric  | $29,562 - $104,581       |
| Usage            | Planned weekly usage frequency                     | Numeric  | 2-7 times per week       |
| Miles            | Expected weekly miles                              | Numeric  | 21-360 miles             |
| Fitness          | Self-rated fitness level                          | Ordinal  | 1-5 scale                |

### Fitness Scale Definition
Self-rated fitness levels are defined as:
1. Poor shape
2. Below average shape
3. Average shape
4. Above average shape
5. Excellent shape

## Analysis Approach

### Key Research Questions
1. What are the demographic characteristics of customers for each product?
2. How do usage intentions vary across products?
3. Is there a relationship between fitness levels and product choice?
4. How does income correlate with product selection?

### Suggested Analyses
1. **Descriptive Statistics**
   ```python
   import pandas as pd
   
   # Load the dataset
   df = pd.read_csv('CardioGoodFitness.csv')
   
   # Get summary statistics by product
   summary_by_product = df.groupby('Product').agg({
       'Age': ['mean', 'std'],
       'Income': ['mean', 'std'],
       'Usage': ['mean', 'std'],
       'Miles': ['mean', 'std'],
       'Fitness': ['mean', 'std']
   })
   ```

2. **Customer Segmentation**
   ```python
   # Example segmentation by product and fitness level
   segment_analysis = df.groupby(['Product', 'Fitness']).size().unstack()
   ```

3. **Demographics Analysis**
   ```python
   # Gender distribution by product
   gender_dist = pd.crosstab(df['Product'], df['Gender'], normalize='index')
   ```

## Data Quality Notes
- All fields are required and contain no missing values
- Income values are in US dollars
- Education is measured in completed years
- Miles represents expected weekly usage

## Project Structure
```
📦 cardio-good-fitness
 ┣ 📂 data
 ┃ ┗ 📜 CardioGoodFitness.csv
 ┣ 📂 notebooks
 ┃ ┗ 📜 customer_analysis.ipynb
 ┣ 📂 reports
 ┃ ┗ 📜 market_research_findings.pdf
 ┗ 📜 README.md
```

## Usage Instructions

### Required Dependencies
```python
pandas==1.5.3
numpy==1.23.5
matplotlib==3.7.1
seaborn==0.12.2
```

### Basic Data Loading
```python
import pandas as pd

# Read the dataset
df = pd.read_csv('data/CardioGoodFitness.csv')

# Display basic information
print(df.info())
```

## Contributing
The market research team welcomes contributions:
1. Additional statistical analyses
2. Customer insight reports
3. Visualization improvements
4. Documentation enhancements

## For AdRight Team Members
- Data updates should be reported to the market research team lead
- Analysis notebooks should be reviewed before committing
- Maintain customer privacy and data confidentiality



## License
This dataset is provided for educational and research purposes.

## Contact
<p align="center">
  <a href="mailto:engrmumtazali01@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
  <a href="https://www.linkedin.com/in/mumtaz-ali"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
  <a href="https://www.instagram.com/its_maliyzi"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white"/></a>
  <a href="https://x.com/mumtazali1223/status/1846913595021328672?s=51"><img src="https://img.shields.io/badge/X-1DA1F2?style=for-the-badge&logo=x&logoColor=white"/></a>
  <a href="https://discord.gg/DZgwHzEb"><img src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white"/></a>
  <a href="https://wa.me/923476338292" target="_blank"><img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white"/></a>
</p>

<p align="center">Made with ❤️ by Mumtaz Ali</p>

---
*Note: This README is part of a data analysis project focusing on customer behavior in fitness equipment purchases.*
