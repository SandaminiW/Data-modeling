# Data-modeling
Data modeling in Power BI 

## DATA MODELING

Data modeling in Power BI is a crucial step in building effective and insightful reports and dashboards. It involves shaping and transforming your data to create a structured and optimized data model that supports the visualization and analysis requirements of your business.

The purpose of data modeling in Power BI is to create a structured, optimized and meaningful representation of your data to support effective analysis, reporting and visualization. Data modeling is a critical step in the Power BI workflow that transform raw data into actionable insights for decision-making and business intelligence.


orders =	Fact Table
customers =	Dimension Table
delivery_status =	Dimension Table
payment_mode = Dimension Table
products =	Dimension Table
sellers =	Dimension Table
reviews =	Dimension Table


## FACT & DIMENSION TABLE

Fact Table-:

•	Also, Calles as Data or Master Table
•	A fact table contains the quantitative data that represents business transactions or events. It typically holds the numeric measures or metrics that you want to analyze, such as sales revenue, quantity sold, profit or expenses.
•	Each row in the fact table corresponds to a specific event or transaction and includes foreign keys that link to the related dimension tables. These foreign keys represent the context of the event and allow you to slice and dice the data along different dimensions.
•	Fact tables are often large in size and can grow rapidly over time, as they store detailed data at the most granular level.
•	A Fact Table contains Foreign Key
Example: Consider an e-commerce business. The fact table could contain information about each individual purchase, such as the product sold, the quality purchased, the sales amount, the date of purchase, and foreign keys pointing to the related dimension tables like Customer, Product and Time.

Dimension Table-:

•	Also called as Lookup Table or Mapping Table
•	Dimension table contain descriptive attributes that provide context to the measures in the fact table. They provide a way to categorize, filter and group the data in the fact table.
•	Dimension tables typically have fewer rows compared to fact tables and store attributes like customer names, product categories, geographic locations, time periods and other qualitative information.
•	Dimension tables are used for slicing and dicing the data, providing meaningful labels to the data points in the fact table, and offering the ability to drill down into more detailed information.
•	A Dimension Table contains Primary key which creates a relationship with Fact table foreign key.
Example: Int the e-commerce scenario, dimension tables could include attributes like CustimerID, CustomerName, ProductID, ProductName, Category, Subcategory, LocationID, LocationName, Date and soon.

## CARDINALITIES IN POWER BI

1.	One-to-One (1:1) -: In a one-to-one relationship, each record in the first table is related to only one record in the second table, and vice versa. This type of relationship is relatively rare in data modeling but can be useful in certain situations where you need to split large tables for performance reasons or when you have optional attributes that can be stored in a separate table.
2.	One-to-Many (1: N)-: The one-to-many relationship is the most common type of relationship in data modeling. In this relationship, each record in the first table can be related to multiple records in the second table, but each record in the second table is related to only one record in the first table. This is the standard relationship type used to connect dimension tables to fact tables in a star schema.
3.	Many-to-Many (N: N)-: Many-to-Many relationships are less common and are usually resolved using bridge tables. In a many-to-many relationship, each record in the first table can be related to multiple records in the second table, and vice versa. This type of relationship can create data ambiguity, so it is essential to use bridge tables or DAX measures to resolve the relationship and perform accurate calculations.


## ACTIVE & INACTIVE RELATIONSHIP
Active Relationship: 
1.	An active relationship is the default relationship that Power BI uses when querying the data. It is the primary relationship that determines how tables are related and how data is aggregated in visuals and calculations.
2.	When you create multiple relationships between two tables, Power BI automatically identifies one of them as the active relationship based on the data model’s cardinality and the direction of the relationships.
3.	The active relationship is used for standard calculations, such as summing values, filtering data, and performing aggregations in visuals and measures.


Inactive Relationship: 
1.	An inactive relationship is an additional relationship that is not used by default when querying the data. It is intended to be used selectively, depending on the analysis requirements or user interactions.
2.	The inactive relationship does not affect standard calculations or visuals directly. Instead, it allows you to create custom calculations using the USERELATIONSHIP function in DAX.
3.	The USERELATIONSHIP function enable you to override the active relationship and specify which relationship to use for a specific calculation or visualization. This gives you more control over how data is related and displayed in certain scenarios.


## POINTS TO REMEMBER
Creating data modeling in Power BI requires careful consideration and attention to detail to ensure the accuracy, efficiency and usability of your reports and dashboards.

1.	Data Source Quality:  Ensure that your data source is reliable, clean and consistent. Check for data quality issues such as missing values, duplicates and incorrect data types before importing the data into Power BI.
2.	Data Transformation and Cleanup: Use Power Query Editor to clean and transform your data. Remove unnecessary columns, handle missing data and apply data type conversions appropriately. This step is crucial for preparing the data for analysis.
3.	Relationships: Establish accurate and meaningful relationships between tables. Check the cardinality between tables to avoid incorrect aggregations and results. Make sure the relationships reflect the actual business logic and join keys.
4.	Avoid Many-to-Many Relationships: Try to avoid creating many-to-many relationships as they can lead to data ambiguity and incorrect calculations. Use bridge tables or resolve many-to-many relationships using DAX measures if necessary.
5.	Use Hierarchies Wisely: Create hierarchies to enable users to navigate easily through data, but avoid creating too many levels in a hierarchy, as it may overwhelm users and make the report cluttered.
6.	Data Model Simplification: Keep your data model as simple as possible. Avoid redundant or unnecessary tables and relationships, which can lead to confusion and increased maintenance overhead.
7.	Row-level Security (RLS): Implement row-level security to restrict data access based on user roles and permissions. Define appropriate roles and filters to ensure data privacy.
8.	Optimize for Performance: Optimize your data model for better performance. Use incremental refresh if dealing with large datasets, and be mindful of the number of visuals and data points in the report.
9.	Test Thoroughly: Validate your data model thoroughly to ensure that the relationships, calculations, and visuals are working correctly. Check for data discrepancies and verify the accuracy of key metrics.
10.	Documentation: Document your data model, including relationships, calculations, and data sources. This documentation will be valuable for you and other team members who work on the report in the future. Data Refresh: Set up scheduled data refresh to ensure that your reports always display the most up-to-date information.
11.	Version Control: If you work in a team, use version control for your Power BI files to track changes and avoid accidental data model modifications.
