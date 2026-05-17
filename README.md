# MIS-311

1: Data overview
<li>	Context & Background: This dataset captures international tourism arrivals across various global destinations. It tracks predictive arrival data for 2024 alongside historical actuals from 2022 and 2023, supplemented by baseline metrics from the World Bank. It allows for an analysis of global travel hubs and pandemic recovery tracking.
<li>	Data Source: The dataset compiles public tourism data, including tracking metrics directly attributed to the World Bank.
<li>	Dimensions: The dataset contains 229 rows and 6 columns.
Column Definitions
<li>	Country: Name of the destination country/territory.
<li>	MostVisited_NumOfArrivalsPredictive_Millions_2024 (float64): Predicted number of international tourist arrivals in millions for the year 2024.
<li>	MostVisited_NumOfArrivals_Millions_2023 (float64):  Actual number of international tourist arrivals in millions for the year 2023.
<li>	MostVisited_NumOfArrivals_Millions_2022 (float64): Actual number of international tourist arrivals in millions for the year 2022.
<li>	MostVisited_NumofArrivals_WorldBank (float64): Annual international tourist arrivals as reported by the World Bank.
MostVisited_DataYear_WorldBank (int): Year for which the World Bank data on international tourist arrivals is provided.

2: 
Missing Values Assessment: A completeness review indicates that while core identifiers like country are 100% complete, reporting levels vary drastically by year. The predictive 2024 column contains 50 active records (156 missing), 2023 contains 49 active records, and 2022 contains 20 active records. The World Bank columns feature 205 records (1 missing).

Handling Strategy: To preserve structural integrity and prevent losing valid baseline metadata for countries, pairwise deletion is used. Blank tracking cells are maintained as empty entries rather than zero-filled, allowing mathematical formulas to naturally omit non-reporting periods without corrupting metrics.

Duplicate Rows Assessment: A strict structural identity scan revealed exactly 3 duplicate rows in the spreadsheet: redundant secondary entries for Eritrea, Montenegro, and Brunei.

Handling Strategy: These 3 redundant rows were systematically removed to eliminate double-counting and artificially inflated metrics, resulting in a clean, finalized dataset of 203 unique rows.
