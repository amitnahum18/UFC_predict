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
```

⚠️ Important Notes:

Fighter names in BOUT must exactly match the names in the dataset (including spelling and order). Otherwise, the model will fail to retrieve historical data for prediction.

Fields like DETAILS, URL, and METHOD are not essential for prediction and can be changed or left blank if needed.
```python
data = {
    "EVENT": ["UFC 318: Holloway vs. Poirier 3"],
    "BOUT": ["Ilia Topuria vs. Islam Makhachev"],
    "OUTCOME": ["W/L"],
    "WEIGHTCLASS": ["Lightweight Bout"],
    "METHOD": ["Decision - Unanimous"],
    "ROUND": [3],
    "TIME": ["5:00"],
    "TIME FORMAT": ["3 Rnd (5-5-5)"],
    "REFEREE": ["Kerry Hatley"],
    "DETAILS": ["Derek Cleary 28 - 29. Eric Colon 28 - 29. Junich..."],
    "URL": ["http://ufcstats.com/fight-details/a95b03e9b5a9"]
}

```
⚠️ Limitations
The model is currently trained on data up to UFC 318. Any fighters or events introduced after this point are not supported.

For new or young fighters with very few or no past fights in the dataset, the model may not be able to produce accurate predictions — or may fail to predict entirely.

If either fighter does not exist in the dataset, the model cannot make a prediction, even if the event is available.

