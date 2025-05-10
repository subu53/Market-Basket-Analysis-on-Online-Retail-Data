# 🛒 Market Basket Analysis - Online Retail

![MBA](https://img.shields.io/badge/Analysis-Market_Basket-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-brightgreen)
![Lift](https://img.shields.io/badge/Top_Lift-24.22-red)

Uncover product association patterns in transactional data from a UK online retailer (2010-2011).

## 📚 Table of Contents
- [🌟 Project Overview](#🌟-project-overview)
- [📂 Dataset](#📂-dataset)
- [🧪 Methodology](#🧪-methodology)
- [📊 Results & Insights](#📊-results--insights)
- [💻 Installation](#💻-installation)
- [🚀 Usage](#🚀-usage)
- [🛠️ Technologies & Libraries](#🛠️-technologies--libraries)
- [🤝 Contributing](#🤝-contributing)
- [📜 License](#📜-license)
- [🙏 Acknowledgements](#🙏-acknowledgements)

## 🌟 Project Overview
This project implements **Market Basket Analysis (MBA)** to discover product associations in transactional data using:
- 📜 Association Rule Mining (Apriori Algorithm)
- 🔍 Transaction pattern analysis
- 📊 Retail analytics techniques

### 🎯 Key Objectives
- Identify strong product associations 🔗  
- Optimize recommendation systems 🤖  
- Improve cross-selling strategies 📈  
- Enhance inventory management 📦  

## 📂 Dataset
**Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail)  
**Period**: December 2010 - December 2011  
**Records**: ~541,909 transactions  
**Format**: CSV (8.7MB)

### 🔑 Key Features
| Feature     | Description                | Type   |
|------------|----------------------------|--------|
| `InvoiceNo` | Transaction identifier      | String |
| `StockCode` | Product identifier          | String |
| `Description` | Product name               | String |
| `Quantity` | Items per transaction        | Integer |
| `UnitPrice` | Price per item (£)          | Float  |
| `CustomerID` | Customer identifier        | String |
| `Country` | Customer location            | String |

## 🧪 Methodology

1. **Data Cleaning**  
   - Handle missing values (`CustomerID`, `Description`)  
   - Remove canceled transactions (`InvoiceNo` starting with 'C')  
   - Filter out negative quantities and invalid prices  

2. **Transaction Encoding**  
   - Convert transactions into a one-hot encoded matrix  

3. **Frequent Itemset Generation**  
   - Apply the **Apriori Algorithm** with a minimum support threshold  

4. **Association Rule Generation**  
   - Extract meaningful relationships between co-purchased items  

5. **Analysis & Insights**  
   - Evaluate rules using **Support**, **Confidence**, and **Lift**  
   - Identify high-impact associations for business strategies  

## 📊 Results & Insights

### 🏆 Top Association Rules

| **Antecedents**                        | **Consequents**                    | **Support** | **Confidence** | **Lift** |
|----------------------------------------|------------------------------------|------------|---------------|-----------|
| PINK REGENCY TEACUP...                 | GREEN REGENCY TEACUP AND SAUCER   | 0.0205     | 0.8903        | 24.22     |
| GREEN REGENCY TEACUP AND SAUCER        | PINK REGENCY TEACUP...             | 0.0205     | 0.5572        | 24.22     |
| PINK REGENCY TEACUP AND SAUCER         | GREEN REGENCY TEACUP AND SAUCER   | 0.0243     | 0.8195        | 22.29     |
| GREEN REGENCY TEACUP AND SAUCER        | PINK REGENCY TEACUP AND SAUCER    | 0.0243     | 0.6601        | 22.29     |
| ROSES REGENCY TEACUP AND SAUCER        | GREEN REGENCY TEACUP AND SAUCER   | 0.0286     | 0.7021        | 19.10     |

### 🔍 Key Findings
- **🏆 Exceptional Lift Values:** 19-24x higher co-occurrence than random chance  
- **🔄 Reciprocal Relationships:** Strong mutual influence between color variants  
- **💡 Cross-Selling Hotspot:** Regency teacup sets show the strongest associations  

### 📊 Metric Analysis
- **📦 Support:** 2-3% of transactions contain these combinations  
- **🎯 Confidence:** Up to 89% likelihood of purchasing consequent with antecedent  
- **🚀 Lift:** Indicates highly non-random purchasing patterns

## 🙋‍♂️ Author

Sammy S. Mutuku  
📍 Nairobi, Kenya | 🌐 [LinkedIn](https://www.linkedin.com/in/samsubu/) | 💻 [GitHub](https://github.com/subu53)  
📧 subusam5@gmail.com
