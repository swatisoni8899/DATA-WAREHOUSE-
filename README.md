# 🧳 Travel & Tourism Data Warehouse Project

A comprehensive data engineering project that demonstrates the end-to-end process of building a scalable **Data Warehouse** for the **Travel and Tourism** domain. The project integrates and analyzes diverse datasets using **PySpark** on **Databricks**, leveraging both **Normalized** and **Dimensional Modeling (Star Schema with SCD Type 2)** techniques to enable business intelligence (BI) and analytical reporting.

---

## 🚀 Project Objective

The primary objective of this project is to create a **scalable**, **efficient**, and **high-quality** data warehouse solution that facilitates:
- Analytical insights into tourist behavior.
- Optimized decision-making for stakeholders in the tourism industry.
- Improved marketing strategies, customer experiences, and operational efficiencies.

---

## 🗂️ Data Sources

The datasets were synthetically generated using Python's **Faker** library and simulate realistic data to represent different facets of the tourism lifecycle:

| Dataset                | Format | Records | Description                                         |
|------------------------|--------|---------|-----------------------------------------------------|
| Tourist Demographics   | JSON   | 1,000+  | Personal and demographic info about tourists.      |
| Flight Bookings        | CSV    | 1,000+  | Reservation details of tourist flight bookings.    |
| Hotel Stays            | CSV    | 1,000+  | Accommodation booking data of tourists.            |
| Attractions Visited    | CSV    | 1,000+  | Information on attraction visits, revenues, etc.   |

---

## 🔨 Tools & Technologies
- **PySpark**: For large-scale data processing and ETL.
- **Databricks Community Edition**: Unified data analytics platform for building and deploying the ETL pipelines.
- **Delta Lake**: Used for storing processed data in an efficient and scalable format.
- **Jupyter Notebook**: Used to simulate and generate synthetic data.

---

## 🛠️ Project Architecture

1. **Data Generation & Collection**  
   Synthetic datasets were created using the Python Faker library to simulate realistic data for tourists, flights, hotels, and attractions.

2. **Data Preprocessing & Normalization (3NF)**  
   The data was cleaned and transformed into a **Normalized Schema (Third Normal Form)** to ensure data consistency and eliminate redundancy. Surrogate keys were generated using `monotonically_increasing_id()`.

3. **Dimensional Modeling (Star Schema)**  
   Leveraging **Kimball’s methodology**, a **Star Schema** was implemented with **Slowly Changing Dimensions (SCD) Type 2** on the `dim_tourist` dimension for tracking historical data.

4. **ETL Pipeline**  
   Implemented on Databricks using PySpark, the pipeline:
   - Extracts raw data from CSV/JSON files.
   - Transforms data into clean dimension and fact tables.
   - Loads data into Delta tables for analytical querying.

---

## ⚙️ Features

- **Normalized Schema**: 
  - Third Normal Form (3NF).
  - Separate dimension tables for cities, hotels, nationalities, and attractions.
  
- **Star Schema Design**:
  - Fact Tables: `flight_bookings`, `hotel_stays`, `attractions_visited`.
  - Dimension Tables: `dim_tourist`, `dim_city`, `dim_hotel`, `dim_attraction`.
  
- **Slowly Changing Dimension (SCD) Type 2**:
  - Preserves historical changes in dimension data.
  - Includes `start_date`, `end_date`, and `is_current` flags.
  
- **Data Quality Assurance**:
  - Null, blank, and NaN checks.
  - Duplicate primary key validation.
  - Foreign key integrity checks.
  - Domain and range validation for dates and numeric fields.

---

## 🔧 How to Run the Project

### Prerequisites
- Databricks Community Edition account.
- Basic understanding of PySpark and Delta Lake.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/swatisoni8899/DATA-WAREHOUSE-.git

2. Upload the datasets to dbfs:/FileStore/ on Databricks.

3. Run the provided notebook in Databricks to:
    Generate normalized tables.
    Create the dimensional model.
    Perform data quality checks.

4. Query the Delta tables using SparkSQL for analysis and reporting.


## 📊 Project Outputs

- **Normalized Data Layer**: Provides consistent and high-integrity data.
- **Dimensional Model (Star Schema)**: Supports BI queries and reporting.

### Sample Analytical Queries
- Popular destinations analysis
- Hotel occupancy and revenue trends
- Attraction visitor insights and revenue generation

---

## 🔮 Future Enhancements

- Integration with BI tools like **Power BI** or **Tableau** for dashboard creation.
- Incremental data ingestion and real-time data pipelines.
- Implement **Data Governance** and **Security** policies.
- Advanced Data Quality Assurance using profiling tools.

---

## 📧 Contact

For questions or collaborations:  
**Swati Soni**  
📧 ssoni16@hswk.iit.edu

