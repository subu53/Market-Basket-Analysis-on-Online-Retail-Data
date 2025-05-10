# 🛒 Market Basket Analysis - Online Retail

![MBA](https://img.shields.io/badge/Analysis-Market_Basket-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-brightgreen)
![Lift](https://img.shields.io/badge/Top_Lift-24.22-red)

Uncover product association patterns in transactional data from a UK online retailer (2010-2011).

## 📚 Table of Contents
- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Results](#-results--insights)
- [Installation](#-installation)
- [Usage](#-usage)
- [Technologies](#-technologies--libraries)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgements](#-acknowledgements)

## 🌟 Project Overview
This project implements **Market Basket Analysis (MBA)** to discover product associations in transactional data using:
- Association Rule Mining (Apriori Algorithm)
- Transaction pattern analysis
- Retail analytics techniques

**Key Objectives**:
- 🎯 Identify strong product associations
- 🤖 Optimize recommendation systems
- 📈 Improve cross-selling strategies
- 📦 Enhance inventory management

## 📂 Dataset
**Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail)  
**Period**: December 2010 - December 2011  
**Records**: ~541,909 transactions  
**Format**: CSV (8.7MB)

### 🔑 Key Features
| Feature | Description | Type |
|---------|-------------|------|
| `InvoiceNo` | Transaction identifier | String |
| `StockCode` | Product identifier | String |
| `Description` | Product name | String |
| `Quantity` | Items per transaction | Integer |
| `UnitPrice` | Price per item (£) | Float |
| `CustomerID` | Customer identifier | String |
| `Country` | Customer location | String |

## 🧪 Methodology
    A[Raw Data] --> B[Data Cleaning]
    B --> C[Transaction Encoding]
    C --> D[Apriori Algorithm]
    D --> E[Rule Generation]
    E --> F[Analysis &amp; Insights]

# Data Preprocessing and Association Rule Mining

## Overview
This script cleans the dataset, encodes transactions, and applies the Apriori algorithm to discover frequent itemsets and association rules.

## Requirements
Ensure you have the necessary dependencies installed before running the script:

```bash
pip install mlxtend pandas numpy

# Import necessary libraries
import pandas as pd
from mlxtend.frequent_patterns import apriori, association_rules

# Load dataset (assuming df is already defined)
# Data Cleaning
df = df[df['Quantity'] > 0]
df = df.dropna(subset=['CustomerID'])

# Transaction Encoding
basket = (df.groupby(['InvoiceNo', 'Description'])['Quantity']
          .sum().unstack().reset_index()
          .fillna(0).set_index('InvoiceNo'))

# Association Rule Mining
frequent_itemsets = apriori(basket, min_support=0.02, use_colnames=True)
rules = association_rules(frequent_itemsets, metric="lift", min_threshold=1)

# Display results
print("Frequent Itemsets:")
print(frequent_itemsets)

print("\nAssociation Rules:")
print(rules)

## 📊 Results & Insights
# Top Association Rules

Antecedents	                Consequents	            Support	Confidence	Lift
PINK REGENCY TEACUP...	GREEN REGENCY TEACUP AND SAUCER	0.0205	0.8903	24.22
GREEN REGENCY TEACUP AND SAUCER	PINK REGENCY TEACUP...	0.0205	0.5572	24.22
PINK REGENCY TEACUP AND SAUCER	GREEN REGENCY TEACUP AND SAUCER	0.0243	0.8195	22.29
GREEN REGENCY TEACUP AND SAUCER	PINK REGENCY TEACUP AND SAUCER	0.0243	0.6601	22.29
ROSES REGENCY TEACUP AND SAUCER	GREEN REGENCY TEACUP AND SAUCER	0.0286	0.7021	19.10

Key Findings 🔍:

🏆 Exceptional Lift Values: 19-24x higher co-occurrence than random chance

🔄 Reciprocal Relationships: Strong mutual influence between color variants

💡 Cross-Selling Hotspot: Regency teacup sets show strongest associations

Metric Analysis:

📦 Support: 2-3% of transactions contain these combinations

🎯 Confidence: Up to 89% likelihood of buying consequent with antecedent

🚀 Lift: Indicates extremely non-random purchasing patterns

💻 Installation
bash
git clone https://github.com/yourusername/market-basket-analysis.git
cd market-basket-analysis
pip install -r requirements.txt
Requirements:

text
pandas>=1.3.5
numpy>=1.21.4
mlxtend>=0.19.0
matplotlib>=3.5.0
seaborn>=0.11.2
🚀 Usage
Run analysis:

python
python mba_analysis.py \
  --input data/online_retail.csv \
  --min_support 0.02 \
  --min_lift 15
Generate visualizations:

python
python visualize_rules.py --input results/rules.csv
🛠️ Technologies & Libraries
Core: Python 3.8+, Jupyter Notebook

Data Processing: pandas, NumPy

ML: mlxtend

Visualization: Matplotlib, Seaborn

Utilities: argparse, warnings

🤝 Contributing
Fork the repository

Create your feature branch (git checkout -b feature/NewFeature)

Commit changes (git commit -m 'Add NewFeature')

Push to branch (git push origin feature/NewFeature)

Open a Pull Request

## 🙋‍♂️ Author


📜 License
MIT License - see LICENSE for details

🙏 Acknowledgements
Data Source: Dr Daqing Chen, Director: Public Analytics group. chend@lsbu.ac.uk

UCI Machine Learning Repository

mlxtend library contributors

## 🙋‍♂️ Author

Sammy S. Mutuku  
📍 Nairobi, Kenya | 🌐 [LinkedIn](https://www.linkedin.com/in/samsubu/) | 💻 [GitHub](https://github.com/subu53)  
📧 subusam5@gmail.com
