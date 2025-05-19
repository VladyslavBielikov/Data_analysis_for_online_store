# Data_analysis_for_online_store
# Sales Data Cleaning and Analysis in Google Colab

This project focuses on preprocessing and exploratory analysis of three datasets: `countries.csv`, `events.csv`, and `products.csv`.

## Key Steps

### 1. Google Drive Integration
All CSV files are loaded from Google Drive into the Colab environment.

### 2. Initial Data Overview

- **Countries** table: Contains country names, ISO codes (alpha-2 and alpha-3), region, and sub-region.  
- **Events** table: Includes order details (dates, priority, country code, product ID, sales channel, units sold, unit price, unit cost).  
- **Products** table: Contains product ID and item type.

**Key columns for merging:**

- `alpha-3` (from `Countries`) = `Country Code` (from `Events`)  
- `Product ID` (from `Events`) = `id` (from `Products`)  

### 3. Missing Data Handling

- Rows with missing values were removed:
  - Less than **0.4%** in `Countries`
  - Less than **6.2%** in `Events`
  - **No** missing values in `Products`
- Date columns in `Events` were converted to `datetime` format.

### 4. Duplicate Removal

- No duplicates were found in any of the tables.

### 5. Data Merging and Feature Engineering

- All three datasets were merged into one final DataFrame.
- Unnecessary columns were dropped, and some values were standardized.
- New columns created:
  - `Revenue` = `Units Sold` × `Unit Price`
  - `Cost` = `Units Sold` × `Unit Cost`
  - `Profit` = `Revenue` − `Cost`
  - `Order_ship_gap` = Days between `Order Date` and `Ship Date`

### 6. Visual Analysis

#### Profit Analysis by:

- **Product Category**: Highest profits from *Cosmetics* and *Household* products
- **Sub-region**: Lowest profits in *Western Asia*
- **Sales Channel**: Similar profits between *Online* and *Offline*
- **Region**: Highest profits in *Europe*

#### Shipping Time Analysis by:

- Country  
- Sub-region  
- Product Category  
- Region  

---

> Created in Google Colab using Pandas and Matplotlib.
