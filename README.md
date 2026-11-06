# credit-risk-default-engine
A credit risk and portfolio assessment project built with Polars and Python. 

## 1. Context & Dataset Choice
To evaluate consumer default risk under real-world portfolio conditions, this project utilizes the **LendingClub Loan Data** set. 

### Why LendingClub?
* **Benchmark Risk Data:** It represents one of the most comprehensive open financial datasets available, containing complete loan lifecycles, interest rates, debt-to-income (DTI) metrics, and eventual default/charge-off outcomes.
* **Macroeconomic & Cycle Diversity:** Spanning multiple years, the dataset captures shifting credit conditions, regulatory shifts, and borrower behavior patterns across different economic cycles.
* **Scale & Feature Complexity:** Containing over **2 million loan records** and 100+ raw attributes, it mimics the scale and tabular complexity encountered in retail banking portfolios.

### Handling Scale: The Shift to Polars LazyFrames
In-memory pandas operations on multi-gigabyte tabular datasets often lead to severe RAM overhead and slow execution during feature aggregation. 

To overcome this:
* The ingestion and preprocessing pipeline is built entirely on **Polars LazyFrames**.
* Operations are compiled into an optimized execution graph before evaluation, enabling streaming processing and memory-efficient aggregations on the raw LendingClub tables.
