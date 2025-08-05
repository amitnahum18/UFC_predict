#  UFC Fight Prediction (Accuracy: 76.4%)

This project predicts the outcomes of UFC fights using scraped fight statistics and a pre-trained model.

##  Accuracy
✅ Model Accuracy: **76.4%**

---

##  Requirements

Before running the prediction script, make sure you have all the required CSV data files and the trained model.

###  Data Source
Data is scraped using this repository:  
➡️ https://github.com/Greco1899/scrape_ufc_stats

---

##  Setup Instructions

1. **Download the required CSV files** from the above GitHub repository:
   - `ufc_fight_stats.csv`
   - `ufc_fight_details.csv`
   - `ufc_fight_results.csv`
   - `ufc_fighter_tott.csv`
   - `ufc_event_details.csv`
   - `df_result4.csv`

2. **Download the trained model file** (e.g., `.cbm`, `.pkl`, or as provided).

3. **Place the files in your working directory** (e.g., `/content/` if using Google Colab).

---

##  Load the Data
The training file and the prediction file are loaded in the same way, except that the training file does not require the df_result4 file.
Make sure to update the file paths in the code to match the location of your CSV files:

```python
import pandas as pd

df_stat_fighter = pd.read_csv("/content/ufc_fight_stats.csv")
# df_main = pd.read_csv("/content/ufc_fight_details.csv")  # optional
df_result = pd.read_csv("/content/ufc_fight_results.csv")
df_tott = pd.read_csv("/content/ufc_fighter_tott.csv")
df_event = pd.read_csv("/content/ufc_event_details.csv")
df_result4 = pd.read_csv("/content/df_result4.csv")
