# Power BI Assignment 1 - Data Transformation & Data Modeling

## 📋 Project Overview

This project demonstrates **data preparation, transformation, and modeling** using Microsoft Power BI and Power Query Editor. The assignment involves working with an e-commerce sales dataset to build a comprehensive data model with proper relationships, calculated columns, and aggregations.

**Course**: Data Analytics (DA) | **Module**: 2  
**Focus**: Data Import, Transformation, Cleansing, and Relationship Modeling

---

## 📊 Dataset Description

The project utilizes three interconnected datasets:

### 1. **List of Orders**
- **Attributes**: Order ID, Order Date, Customer Name, City, State, Category, Amount, Profit
- **Purpose**: Contains order-level transaction data with geographic and financial information

### 2. **Order Details**
- **Attributes**: Order ID, Category, Sub-Category, Quantity, Amount, Profit
- **Purpose**: Provides product-level details for each order

### 3. **Sales Target**
- **Attributes**: Category, Month of Order Date, Target
- **Purpose**: Contains performance benchmarks for sales targets by category and month

---

## 🎯 Tasks Completed

### **Task 1-2: Data Import & Data Types**
- ✅ Imported all three CSV files into Power Query Editor
- ✅ Limited List of Orders to first 500 rows for manageable dataset size
- ✅ Set Order Date column to Date data type
- ✅ Changed Amount and Target columns to fixed decimal numbers

### **Task 3: Text Formatting**
- ✅ Converted CustomerName column to Proper Case for consistent capitalization
- ✅ Ensured uniform text formatting across all records

### **Task 4: Column Creation**
- ✅ **Location Column**: Merged City and State in format "City, State"
- ✅ **Profit Margin Column**: Calculated as (Profit / Amount) × 100 for percentage-based profitability analysis

### **Task 5: Conditional Column**
- ✅ **Profit Status Column**: Categorized based on profit values:
  - Loss (Profit < 0)
  - Break-Even (Profit = 0)
  - Profit (Profit > 0)

### **Task 6: Data Merging**
- ✅ Merged List of Orders with Order Details using Order ID
- ✅ Created consolidated "Orders Data" table combining order and product information

### **Task 7: Data Quality Handling**
- ✅ Identified and documented missing values across all tables
- ✅ Applied appropriate strategies for handling nulls and duplicates
- ✅ Ensured data consistency and integrity

### **Task 8: Sorting & Filtering**
- ✅ Sorted Orders Data by Order Date in descending order
- ✅ Applied state-based filters (e.g., Tamil Nadu) for targeted analysis
- ✅ Demonstrated filtering capabilities for business insights

### **Task 9: Aggregation & Grouping**
- ✅ **OrderID_Count**: Count of orders by category
- ✅ **Category_AverageProfit**: Average profit values by category
  - Furniture: 9.46%
  - Clothing: 11.76%
  - Electronics: 34.07%
- ✅ **Total_amount_Subcategory**: Total sales by sub-category
- ✅ **Monthly_Target**: Aggregated targets by month

### **Task 10: Data Modeling**
- ✅ Established One-to-Many relationship: List of Orders → Order Details (Order ID)
- ✅ Established Many-to-One relationship: Order Details ↔ Sales Target (Category)
- ✅ Configured all relationships as active for proper filtering
- ✅ Verified model integrity through Manage Relationships

---

## 🔄 Data Transformation Logic

### **1. Data Cleaning**
```
Original Data → Remove nulls/duplicates → Standardized format → Clean Data
```

### **2. Text Standardization**
```
CustomerName: "john smith" → Proper Case → "John Smith"
```

### **3. Geographic Enrichment**
```
City: "Chennai" + State: "Tamil Nadu" → Merge → Location: "Chennai, Tamil Nadu"
```

### **4. Financial Calculations**
```
Profit Margin = (Profit ÷ Amount) × 100 %
Example: Profit: $100, Amount: $500 → Profit Margin: 20%
```

### **5. Business Logic Categorization**
```
IF Profit < 0 THEN "Loss"
IF Profit = 0 THEN "Break-Even"
IF Profit > 0 THEN "Profit"
```

### **6. Data Aggregation**
```
Transaction Level → Grouping by Category/Sub-Category/Month → Summary Level
```

---

## 📐 Data Model Architecture

### **Star Schema Design**

```
                    List of Orders
                          |
                     (Order ID)
                          |
                    Orders Data
                     (Fact Table)
                          |
                     (Category)
                          |
                    Sales Target
              (Dimension/Reference Table)
```

### **Relationships**
| From Table | To Table | Key | Type | Status |
|-----------|----------|-----|------|--------|
| List of Orders | Order Details | Order ID | One-to-Many | Active |
| Order Details | Sales Target | Category | Many-to-One | Active |

### **Benefits of This Model**
- ✅ Eliminates data redundancy
- ✅ Enables cross-filtering between dimensions
- ✅ Supports drill-down analysis
- ✅ Maintains referential integrity
- ✅ Optimizes query performance

---

## 📂 Deliverables

### **1. Power BI File (.pbix)**
Contains:
- Imported and transformed datasets
- All Power Query transformations and custom columns
- Merged tables (Orders Data)
- Active data model relationships
- Aggregated queries for analysis

### **2. Documentation Files**
- **README.md**: Project overview and technical documentation
- **TRANSFORMATION_LOGIC.md**: Detailed transformation steps
- **Screenshots**: Visual evidence of all tasks (1-10)
- **Data_Model_View.png**: Relationship diagram

---

## 🛠️ Technologies & Tools Used

- **Microsoft Power BI Desktop**: Data modeling and visualization platform
- **Power Query Editor**: ETL (Extract, Transform, Load) operations
- **DAX (Data Analysis Expressions)**: Custom calculations and measures
- **Excel/CSV**: Source data format

---

## 📊 Key Metrics & Calculations

### **Profitability Analysis**
| Category | Average Profit | Profit Margin |
|----------|----------------|---------------|
| Furniture | 9.46% | Variable |
| Clothing | 11.76% | Variable |
| Electronics | 34.07% | Highest |

### **Sales Performance**
- Total Orders Analyzed: 500 rows
- Product Sub-Categories: 17
- Monthly Data Points: 12 months
- Geographic Coverage: Multiple states

---

## 🚀 How to Use This Project

### **Prerequisites**
- Microsoft Power BI Desktop (latest version)
- Sample CSV files (List of Orders, Order Details, Sales Target)

### **Steps to Open**
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/PowerBI-Assignment1.git
   cd PowerBI-Assignment1
   ```

2. Open the Power BI file:
   - Launch Power BI Desktop
   - Open `PowerBI_Assignment1.pbix`

3. Explore the data model:
   - Navigate to the "Model" view
   - Review relationships and table structure
   - Check Power Query transformations

4. View reports and visualizations:
   - Multiple pages with charts and KPIs
   - Filter by state, category, and date range
   - Analyze profit margins and sales targets

---

## 📈 Skills Demonstrated

| Skill Area | Sub-Skills | Level |
|-----------|-----------|-------|
| **Data Preparation** | Data Loading, Import | Beginner ✓ |
| **Data Cleaning** | Data Types, Text Formatting | Beginner ✓ |
| **Business Logic** | Custom Columns, Conditional Columns | Beginner ✓ |
| **Data Integration** | Merging, Joins | Intermediate ✓ |
| **Data Quality** | Null Handling, Deduplication | Intermediate ✓ |
| **Data Exploration** | Filtering, Sorting | Beginner ✓ |
| **Data Analysis** | Grouping, Aggregation | Intermediate ✓ |
| **Data Modeling** | Relationships, Schema Design | Intermediate ✓ |

---

## 📋 Evaluation Rubric

| Component | Marks | Criteria |
|-----------|-------|----------|
| Data Import & Transformation | 3 | Correct data types, formatting, columns |
| Aggregation & Filtering | 3 | Proper grouping, sorting, filtering logic |
| Data Merging & Quality | 2 | Accurate joins, data validation |
| Data Modeling | 2 | Active relationships, correct configuration |
| **Total** | **10** | **Complete & accurate implementation** |

---

## 🎓 Learning Outcomes

After completing this assignment, you will understand:

✅ How to import and structure multiple data sources  
✅ Data transformation best practices using Power Query  
✅ Creating calculated and conditional columns for business logic  
✅ Merging and joining tables effectively  
✅ Identifying and handling data quality issues  
✅ Building robust data models with proper relationships  
✅ Aggregating data for analytical insights  
✅ Using DAX for custom calculations  

---

## 📝 Project Structure

```
PowerBI-Assignment1/
│
├── PowerBI_Assignment1.pbix          # Main Power BI file
├── README.md                          # Project documentation
├── TRANSFORMATION_LOGIC.md            # Detailed transformation guide
│
├── Data_Sources/
│   ├── List_of_Orders.csv            # Original order data
│   ├── Order_Details.csv             # Product-level details
│   └── Sales_Target.csv              # Target benchmarks
│
└── Screenshots/
    ├── Task_1_2_3_DataImport.png
    ├── Task_4_5_6_Columns.png
    ├── Task_7_8_Quality.png
    ├── Task_9_Aggregation.png
    ├── Task_10_DataModel.png
    └── Model_Relationships.png
```

---

## 🔍 Key Insights from Analysis

- **Electronics category** shows highest average profit margin (34.07%)
- **Data quality**: Minimal missing values with documented handling strategies
- **Geographic distribution**: Orders across multiple states with location consolidation
- **Temporal analysis**: 12 months of data allowing monthly trend analysis
- **Product diversity**: 17 sub-categories providing detailed segmentation

---

## 📞 Support & Questions

For questions or issues:
1. Review the `TRANSFORMATION_LOGIC.md` file for detailed steps
2. Check Power Query transformations in the Power BI file
3. Refer to the model diagram in the Model view
4. Review screenshots for visual reference

---

## 📄 License

This project is submitted as coursework for the Data Analytics Module.  
Please refer to your institution's policies for usage and distribution.

---

## ✍️ Author & Submission

**Student Name**: [Your Name]  
**Course**: Data Analytics (DA) - Module 2  
**Assignment**: Power BI Assignment 1 - Data Transformation & Data Modeling  
**Date**: [Submission Date]  
**Institution**: [Your Institution]

---

## 🎉 Conclusion

This comprehensive Power BI project demonstrates proficiency in data transformation, cleaning, integration, and modeling. The deliverables showcase a complete end-to-end data preparation workflow suitable for business analytics and reporting.

**Status**: ✅ Complete  
**All Tasks**: ✅ Completed  
**Model Relationships**: ✅ Verified & Active  
**Data Quality**: ✅ Validated

---

**Last Updated**: June 2026  
**Power BI Version**: Latest Desktop Version
