# Flight-Delay-Analytics-with-PySpark-
# Flight Delay Analytics with PySpark

## Project Overview

This project focuses on analyzing a comprehensive flight delays dataset using **Apache PySpark**. The primary goal is to extract meaningful insights, identify patterns, and understand the factors contributing to flight delays. This analysis leverages PySpark's capabilities for scalable data processing and aggregation, demonstrating its effectiveness in handling large datasets.

## Key Objectives

* **Data Ingestion & Preprocessing:** Efficiently load and clean a large-scale flight delay dataset.
* **Exploratory Data Analysis (EDA):** Uncover initial trends and distributions within the data.
* **Insight Generation:** Identify key factors influencing flight delays, such as airline performance, airport efficiency, and seasonal trends.
* **Scalable Aggregations:** Utilize PySpark to perform complex aggregations and derive meaningful metrics.
* **Data Visualization:** Present findings through clear and impactful visualizations.

## Dataset

The analysis was performed on the `Airline_Delay_Cause.csv` dataset. This dataset typically contains information about:
* Flight details (Year, Month, Carrier, Carrier Name, Airport, Airport Name)
* Arrival flight counts (`arr_flights`, `arr_del15`)
* Counts of delays by cause (carrier, weather, National Aviation System (NAS), security, late aircraft)
* Arrival cancellations and diversions
* Total arrival delay minutes and delay minutes broken down by cause.

*(If your dataset is publicly available, provide a link here. If not, briefly describe its source or typical characteristics of such datasets.)*

## Methodology

1.  **Spark Session Initialization:** A PySpark SparkSession was initialized for distributed computing.
2.  **Data Ingestion:** The `Airline_Delay_Cause.csv` file was loaded into a Spark DataFrame, with schema inference.
3.  **Data Cleaning & Preprocessing:**
    * Missing numerical delay values were filled with `0`.
    * Rows with missing essential `airport_name` or `carrier_name` were dropped.
    * Duplicate records were removed.
    * `arr_delay` column was explicitly cast to `float` to ensure correct calculations.
4.  **Scalable Data Analysis (PySpark Aggregations):**
    * **Average Arrival Delay by Airline:** Calculated the average `arr_delay` for each `carrier_name` and ordered by the highest average delay.
    * **On-Time Arrival Rate by Airport:** Determined the proportion of on-time arrivals (`arr_delay <= 0`) for each `airport_name`.
    * **Longest Individual Delays:** Identified the top 5 flights with the longest arrival delays.
    * **Monthly Delay Trends:** Computed the average arrival delay per month to observe seasonal patterns.
5.  **Data Visualization (Matplotlib & Seaborn):**
    * Results from PySpark DataFrames were converted to Pandas DataFrames for plotting.
    * Bar charts were used to visualize top airlines by average delay and top airports by on-time rate.
    * A line plot displayed the average arrival delay by month.
    * An additional bar plot showed the top 5 longest individual delays.

## Insights Displayed

The analysis revealed several key insights:

* **Top/Bottom Performing Airlines:** Identified airlines with the highest and lowest average arrival delays, potentially highlighting operational efficiencies or recurring issues. (e.g., Southwest Airlines Co. and American Airlines Inc. showed the highest average delays among the top 10 rows displayed.)
* **Airport On-Time Performance:** Showcased airports with the best on-time arrival rates, suggesting varying levels of efficiency or unique operational characteristics (e.g., Tokeen, AK: Tokeen Airport and Macon, GA: Middle Georgia Regional had a 1.0 on-time arrival rate in the top 10).
* **Extreme Delay Events:** Pinpointed specific flights with exceptionally long delays, often associated with major airlines and large hubs (e.g., American Airlines Inc. at Dallas/Fort Worth and Delta Air Lines Inc. at Hartsfield-Jackson Atlanta).
* **Seasonal Delay Trends:** Illustrated how average delays fluctuate throughout the year, with notable peaks (e.g., June and July showed higher average delays).

## Technologies Used

* **Python**
* **PySpark** (for data processing and analysis)
* **Pandas** (for data manipulation and conversion to plotting)
* **Matplotlib** (for static visualizations)
* **Seaborn** (for enhanced statistical visualizations)

## How to Run (Local Setup)

1.  **Prerequisites:**
    * Ensure Java is installed (`java -version`).
    * Install PySpark: `pip install pyspark`
    * Install other libraries: `pip install pandas matplotlib seaborn`
2.  **Dataset:** Place the `Airline_Delay_Cause.csv` file in the same directory as the Jupyter Notebook.
3.  **Run:** Open `task1.ipynb` in a Jupyter environment and run all cells.

## Future Enhancements

* **Cause-Specific Delay Analysis:** Dive deeper into the specific causes of delays (e.g., weather, carrier, NAS) across different airlines and airports.
* **Predictive Modeling:** Build machine learning models to forecast flight delays based on various features.
* **Interactive Dashboard:** Create an interactive dashboard (e.g., using Tableau, Power BI, or Streamlit with PySpark) for more dynamic exploration of insights.
* **Larger Datasets:** Test scalability with significantly larger datasets to evaluate PySpark's performance characteristics more rigorously.
* **External Data Integration:** Incorporate external data sources like real-time weather information or air traffic control data.



