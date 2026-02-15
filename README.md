# ApexPlanet_Task-1
# 📊 Data Cleaning — Retail Orders Dataset

## 📌 Overview

This project cleans a retail orders dataset (`Raw_DataSet.csv`) using Python and pandas.
The goal is to prepare the raw data for analysis by fixing formats, removing invalid records, and dropping duplicates using a defined rule.

---

## 🧾 Dataset Contains

* Order details
* Customer details
* Product details
* Location data
* Sales values
* Order and shipping dates

---

## 🧹 Cleaning Steps Performed

* Cleaned column names (lowercase, removed spaces)
* Trimmed extra spaces in text fields
* Converted date columns to datetime:

  * `order_date`
  * `ship_date`
* Converted **sales** column to numeric
* Removed rows with:

  * negative sales
  * invalid sales values
* Fixed **postal_code**:

  * converted to text
  * removed `.0`
* Created new column:

  * `shipping_days = ship_date − order_date`
* Removed rows where shipping days were negative

---

## 🔁 Duplicate Removal Rule

Rows were treated as duplicates when all these fields matched:

```
postal_code + customer_name + order_id + product_name + ship_date
```

* First row kept
* Remaining duplicates removed
* Duplicate rows saved separately for checking

---

## 📂 Output Files

* `train_cleaned.csv` → final cleaned dataset
* `removed_rows.csv` → rows removed during cleaning
* `data_dictionary.xlsx` → column definitions
* `data_dictionary.png` → data dictionary image
* `cleaning_script.py` → Python cleaning code

---

## 🛠 Tools Used

* Python
* pandas
* numpy

---

## ▶️ How to Run

```bash
pip install pandas numpy
python cleaning_script.py
```

---

## ✅ Result

The dataset is now:

* consistent
* duplicate-free (based on defined key)
* correct data types
* ready for analysis or visualization

---
