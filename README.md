# Big Data E‑Commerce Analytics (Hadoop + PySpark)

This project analyzes **42M+ e‑commerce events** (views, add‑to‑cart, purchases) to extract
business insights using **Hadoop** for storage and **PySpark** for processing. Results are
summarized in the notebook and in the accompanying PDF report.

## Repository Contents
- `Big_Data_Project.ipynb` — PySpark/Hadoop notebook with the full pipeline
- `report/Big Data Report.pdf` — Final report with methodology, visuals, and results
- `requirements.txt` — Python dependencies to run the notebook
- `data/` — (empty) placeholder for any small sample data (large datasets should not be committed)

## Dataset
**Ecommerce Behavior Data from Multi‑category Store** (Kaggle) — user interactions captured over ~7 months in 2019:
views, add‑to‑cart, purchases.

> Large data should be downloaded from Kaggle and stored locally/HDFS; do not commit it to Git.

## Pipeline (High‑Level)
1. **Ingest** to HDFS and **load** with PySpark
2. **Preprocess**: map nulls in `brand`, `category_code`; drop duplicates; filter zero‑price outliers; drop unused IDs
3. **Analyze** with grouped aggregations:
   - Event counts (views, carts, purchases)
   - Cart→Purchase conversion
   - Top categories/brands by revenue
   - Highest‑spending users
   - Busiest day of the week
4. **Visualize**: bar/line charts of top categories/brands and traffic

## Key Findings (from the report)
- **Cart→Purchase conversion ≈ 82.7%**
- **Top categories by revenue**: Smartphones (~$5.42B), Notebooks (~$0.81B), TVs (~$0.49B)
- **Top brands by revenue**: Apple (~$3.43B), Samsung (~$1.74B), Xiaomi (~$0.62B)
- **Busiest day**: Tuesday (~7M visits)

## How to Run
```bash
# 1) (Optional) Create a virtual environment
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# 2) Install Python dependencies
pip install -r requirements.txt

# 3) Launch Jupyter
jupyter notebook Big_Data_Project.ipynb
```

> Note: For full big‑data runs you’ll need **Hadoop/HDFS** and a **Spark** cluster or local Spark.
The notebook contains cells designed to run in PySpark (e.g., `SparkSession.builder...`).

## Project Structure
```
big-data-ecommerce-analysis/
├── README.md
├── requirements.txt
├── Big_Data_Project.ipynb
├── report/
│   └── Big Data Report.pdf
└── data/
    └── .gitkeep
```

## Authors
- Omar Zarifa  
  [LinkedIn](https://www.linkedin.com/in/omar-zarifa-36b061ab)

```
