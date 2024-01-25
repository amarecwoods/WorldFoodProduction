# World Food Production Database

This repository contains SQL queries and commands for managing a database named "World_Food" that stores information about food production in various countries.

## Table of Contents
1. [Description](#description)
2. [Queries](#queries)
3. [Data Source](#data-source)
4. [Visualization](#visualization)

## Description
The "World_Food" database includes information on the production of various food items in different countries. The primary table in this database is named "uncleanwf" and contains data fields such as country name, year, and production quantities for different food items like maize, rice, yams, etc.

## Queries
Here are some SQL queries and commands used to manipulate and analyze the data in the "World_Food" database:

### 1. Selecting Data
```sql
SELECT TOP (1000) [Entity], [Year], [Maize_Production_tonnes], [Rice_Production_tonnes], [Yams_Production_tonnes], [Wheat_Production_tonnes], [Tomatoes_Production_tonnes], [Tea_Production_tonnes], [Sweet_potatoes_Production_tonnes], [Sunflower_seed_Production_tonnes], [Sugar_cane_Production_tonnes], [Soybeans_Production_tonnes], [Rye_Production_tonnes], [Potatoes_Production_tonnes], [Oranges_Production_tonnes], [Peas_dry_Production_tonnes], [Palm_oil_Production_tonnes], [Grapes_Production_tonnes], [Coffee_green_Production_tonnes], [Cocoa_beans_Production_tonnes], [Meat_chicken_Production_tonnes], [Bananas_Production_tonnes], [Avocados_Production_tonnes], [Apples_Production_tonnes]
FROM [World_Food].[dbo].[uncleanwf];
-- Deciding on a year to analyze
SELECT Year, COUNT(Year) as occurrence 
FROM World_Food.dbo.uncleanwf
GROUP BY [Year];

-- Selecting specific data for analysis
SELECT 
    Entity,
    Yams_Production_tonnes,
    Rice_Production_tonnes,
    Meat_chicken_Production_tonnes
FROM 
    World_Food.dbo.uncleanwf
WHERE 
    [Year] = '2021';
-- Deleting data for years other than 2021
DELETE FROM World_Food.dbo.uncleanwf 
WHERE Year != '2021';

-- Dropping unnecessary columns
/* ALTER TABLE World_Food.dbo.uncleanwf
DROP COLUMN 
[Wheat_Production_tonnes], [Tomatoes_Production_tonnes], [Tea_Production_tonnes], [Sweet_potatoes_Production_tonnes], [Sunflower_seed_Production_tonnes], [Sugar_cane_Production_tonnes], [Soybeans_Production_tonnes], [Rye_Production_tonnes], [Potatoes_Production_tonnes], [Oranges_Production_tonnes], [Peas_dry_Production_tonnes], [Palm_oil_Production_tonnes], [Grapes_Production_tonnes], [Coffee_green_Production_tonnes], [Cocoa_beans_Production_tonnes], [Bananas_Production_tonnes], [Avocados_Production_tonnes], [Apples_Production_tonnes]; */

-- Renaming columns for better readability
USE World_Food;
EXEC sp_rename 'dbo.uncleanwf.Entity', 'Country', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Rice_Production_tonnes', 'Rice_Tons', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Maize_Production_tonnes', 'Maize_Tons', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Meat_chicken_Production_tonnes', 'Chicken_Tons', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Yams_Production_tonnes', 'Yam_Tons', 'COLUMN';
```markdown
# World Food Production Database

This repository contains SQL queries and commands for managing a database named "World_Food" that stores information about food production in various countries.

## Table of Contents
1. [Description](#description)
2. [Queries](#queries)
3. [Data Source](#data-source)
4. [Visualization](#visualization)

## Description
The "World_Food" database includes information on the production of various food items in different countries. The primary table in this database is named "uncleanwf" and contains data fields such as country name, year, and production quantities for different food items like maize, rice, yams, etc.

## Queries
Here are some SQL queries and commands used to manipulate and analyze the data in the "World_Food" database:

### 1. Selecting Data
```sql
SELECT TOP (1000) [Entity], [Year], [Maize_Production_tonnes], [Rice_Production_tonnes], [Yams_Production_tonnes], [Wheat_Production_tonnes], [Tomatoes_Production_tonnes], [Tea_Production_tonnes], [Sweet_potatoes_Production_tonnes], [Sunflower_seed_Production_tonnes], [Sugar_cane_Production_tonnes], [Soybeans_Production_tonnes], [Rye_Production_tonnes], [Potatoes_Production_tonnes], [Oranges_Production_tonnes], [Peas_dry_Production_tonnes], [Palm_oil_Production_tonnes], [Grapes_Production_tonnes], [Coffee_green_Production_tonnes], [Cocoa_beans_Production_tonnes], [Meat_chicken_Production_tonnes], [Bananas_Production_tonnes], [Avocados_Production_tonnes], [Apples_Production_tonnes]
FROM [World_Food].[dbo].[uncleanwf];
```

### 2. Analyzing Data
```sql
-- Deciding on a year to analyze
SELECT Year, COUNT(Year) as occurrence 
FROM World_Food.dbo.uncleanwf
GROUP BY [Year];

-- Selecting specific data for analysis
SELECT 
    Entity,
    Yams_Production_tonnes,
    Rice_Production_tonnes,
    Meat_chicken_Production_tonnes
FROM 
    World_Food.dbo.uncleanwf
WHERE 
    [Year] = '2021';
```

### 3. Data Management
```sql
-- Deleting data for years other than 2021
DELETE FROM World_Food.dbo.uncleanwf 
WHERE Year != '2021';

-- Dropping unnecessary columns
/* ALTER TABLE World_Food.dbo.uncleanwf
DROP COLUMN 
[Wheat_Production_tonnes], [Tomatoes_Production_tonnes], [Tea_Production_tonnes], [Sweet_potatoes_Production_tonnes], [Sunflower_seed_Production_tonnes], [Sugar_cane_Production_tonnes], [Soybeans_Production_tonnes], [Rye_Production_tonnes], [Potatoes_Production_tonnes], [Oranges_Production_tonnes], [Peas_dry_Production_tonnes], [Palm_oil_Production_tonnes], [Grapes_Production_tonnes], [Coffee_green_Production_tonnes], [Cocoa_beans_Production_tonnes], [Bananas_Production_tonnes], [Avocados_Production_tonnes], [Apples_Production_tonnes]; */

-- Renaming columns for better readability
USE World_Food;
EXEC sp_rename 'dbo.uncleanwf.Entity', 'Country', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Rice_Production_tonnes', 'Rice_Tons', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Maize_Production_tonnes', 'Maize_Tons', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Meat_chicken_Production_tonnes', 'Chicken_Tons', 'COLUMN';
EXEC sp_rename 'dbo.uncleanwf.Yams_Production_tonnes', 'Yam_Tons', 'COLUMN';
```

## Data Source
The data for this project was sourced from [Kaggle](https://www.kaggle.com/datasets/rafsunahmad/world-food-production), a platform for data science and machine learning enthusiasts.

## Visualization
For visualization of the data, you can refer to the [Tableau presentation](https://public.tableau.com/views/2022WorldFoodProduction/Dashboard2?:language=en-US&:display_count=n&:origin=viz_share_link) created using the data from this database.

```

Please note that the SQL commands provided assume familiarity with database management systems like SQL Server. Adjustments may be necessary depending on the specific database system you are using.
