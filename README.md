# Export Forecasting for Warehouse 2  

## **Objective**  
The goal of this case study is to forecast the number of ordered items exported daily to **Warehouse 2** for each country. This is achieved by analyzing sales forecasts and incorporating data from various ordering processes, each governed by different export rules.

---

## **Workflow**  

1. **Data Preparation**  
   - Imported required datasets:
     - **B2C Sales Forecast**  
     - **ICD Sales Forecast**  
     - **SCD Sales Forecast**  
     - **Item Cross-Docking Shifts**  
     - **Blocked Items per ICD Item**  
   - Converted date columns to `datetime` for consistency.  

2. **Data Exploration**  
   - Explored each column of each dataframe created from the datasets.

3. **Tasks Implementation**  
   - **Step 1**: Aggregated B2C and SCD (Shipping & Picking Warehouse) data for **Warehouse 2** based on export rules.  
   - **Step 2**: Calculated ICD forecasts for items sourced from other warehouses to meet **Warehouse 2** demands.  
   - **Step 3**: Estimated the number of items impacted by cross-docking processes.  
   - **Step 4**: Calculated distributed items for each country and exported date based on cross-docking impact.  
   - **Step 5**: Finalized forecasts by combining all components:  
     `B2C + SCD - items_minus + items_plus`.  

---

## **Key Output**  
The final output is a pivot table:  
- **Index**: Countries (`country_code`)  
- **Columns**: Export dates (`exported_at`)  
- **Values**: Forecasted items (`sales_forecast_items`)  

This table provides the daily export forecast to Warehouse 2 for each country.

---

## **How to Run**  
1. Clone the repository.  
2. Create the environment using environment.yml file. Activate the environment: `conda activate aboutyou`
3. Place the datasets in the appropriate `assets/` directory as specified in the notebook or make sure they already present upon cloning the repo.
4. Run the notebooks `01_explore_assets.ipynb` to perform data exporation and `02_tasks_implementation.ipynb` to generate the final output.

---

## **Folder Structure**  
```plaintext

├── assets/  
│   ├── b2c_items_sales_forecast - b2c_items_sales_forecast.csv  
│   ├── icd_items_sales_forecast - icd_items_sales_forecast.csv
│   ├── scd_items_sales_foreecast - scd_items_sales_forecast.csv  
│   ├── item_cross_docking_shift - item_cross_docking_shift.csv  
│   ├── items_blocked_per_cd_item - items_blocked_per_cd_item.csv  
│   ├── Logistics Case Study.docx
├── notebooks/
│   ├── 01_explore_assets.ipynb
│   ├── 02_tasks_implementation.ipynb
├── README.md  
├── environment.yml 