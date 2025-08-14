# Synthetic Data Preparation Summary Report

This report summarizes the methods and steps used to prepare the synthetic dataset in the BigQuery table `mgmt599-rakesh-final-project.superstore.SuperMarketSynth`.

## Methods Used

The synthetic data was generated using the following methods:

* **Sampling from Existing Data Distribution**: Key numerical columns ('Quantity', 'cogs', and 'Rating') were generated based on the mean and standard deviation of the existing data in the `mgmt599-rakesh-final-project.superstore.SuperMarketRaw` table, assuming a normal distribution. Categorical columns were sampled randomly from the existing data.
* **Applying Business Rules/Formulas**: Specific formulas were applied to calculate derived columns based on generated 'Unit price' and 'Quantity' values:
  * 'Tax 5%' = 0.05 * ('Unit Price' * 'Quantity')
  * 'Sales' = ('Unit Price' * 'Quantity') + 'Tax 5%'
  * 'Gross income' = 'Sales' - 'Cogs'
  * 'Gross margin percentage' = ('Gross Income' / 'Sales') * 100
* **Implementing Downward Sales Trend**: A linear scaling factor was applied to the 'Sales' column over time to simulate a slight downward trend in monthly sales from April 2019 to December 2020.
* **Date Range Extension**: Synthetic data was generated for a period extending beyond the original dataset (April 2019 to December 2020) to increase the overall data duration.
* **Quantity Constraint**: The 'Quantity' in the synthetic data was constrained to a maximum of 2.
* **Unit Price Adjustment**: The 'Unit price' in the synthetic data generated for the period from April 2019 to December 2020 was divided by 2.
* **COGS Adjustment**: For the period from April 2019 to December 2020, 'cogs' values were adjusted to be between 2% and 5% less than 'Sales'.

## Steps Taken

The following steps were performed to prepare the synthetic data:

1. **Load Existing Data**: The original data from `mgmt599-rakesh-final-project.superstore.SuperMarketRaw` was loaded into a pandas DataFrame to analyze its distribution.
2. **Analyze Existing Data Distribution**: Mean and standard deviation were calculated for numerical columns in the existing data to serve as parameters for synthetic data generation.
3. **Generate Synthetic Data**: Synthetic records were generated for the period from April 2019 to December 2020, including generating dates, sampling categorical data, and generating numerical data based on the analyzed distributions and the specified quantity constraint and initial unit price adjustment.
4. **Apply Formulas to Synthetic Data**: The formulas for 'Tax 5%', 'Sales', 'Gross income', and 'Gross margin percentage' were applied to the generated synthetic data.
5. **Adjust Synthetic Data for Downward Sales Trend and COGS**: The 'Sales' column in the synthetic data was scaled linearly over time to create a downward monthly sales trend. Additionally, 'cogs' values for the period from April 2019 to December 2020 were adjusted to be between 2% and 5% less than 'Sales', and dependent columns were re-calculated based on the adjusted 'Sales' and 'cogs'.
6. **Combine Existing and Synthetic Data**: The original and synthetic DataFrames were concatenated to create a single combined dataset.
7. **Create BigQuery Table**: A new BigQuery table named `mgmt599-rakesh-final-project.superstore.SuperMarketSynth` was created with a schema matching the combined DataFrame.
8. **Load Combined Data into BigQuery**: The combined DataFrame was loaded into the newly created BigQuery table, replacing any existing data in the table.
9. **Verify Data**: The data in the `mgmt599-rakesh-final-project.superstore.SuperMarketSynth` table was queried to verify the total record count, date range, and confirm the presence of the downward sales trend and the COGS adjustment.

This process resulted in a synthetic dataset of approximately 100,000 records, combined with the original 1,000 records, covering a period of two years with a simulated downward trend in monthly sales, incorporating the specified constraints and adjustments.
