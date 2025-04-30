## 🏎️ F1 Race Finishing Position Predictor

Predict Formula 1 driver finishing positions using real-world race data via the [FastF1 API](https://github.com/theOehrly/Fast-F1), machine learning, and an interactive Streamlit dashboard.  
Built to visualize predictions, stats, and driver performance dynamically with emotional GIF reactions for each race outcome.

---

### 🚀 Features

#### 🎯 Race Finishing Predictor
- Input: Year, Circuit Name, Driver Abbreviation
- Output: Predicted finishing position (e.g., `P1`, `P10`)
- 🔥 Bonus: Driver-specific GIF based on predicted result (win / mid / low)

#### 📊 Driver Performance Insights
- See last 3 race finishes for any current driver
- Uses FastF1 live race data from previous seasons

#### 🏁 Circuit Statistics
- Win history of a given circuit across the last 10 years
- Most frequent winners displayed dynamically

#### 📈 Model Training Dashboard
- Model accuracy and confusion matrix visualized
- Dataset preview
- One-click retrain functionality using latest `raw_data.csv`

---

### 🧠 How It Works

1. **FastF1 API** pulls race results for drivers/circuits from 2018–2024
2. Data is preprocessed and stored in `raw_data.csv`
3. A **RandomForestClassifier** predicts if a driver will win or place lower
4. Streamlit UI provides visual interface for input/output + GIFs

---

### 📁 Project Structure

```
chat_predictor_f1/
├── app/
│   ├── predictor.py
│   ├── driver_gif_map.py
│   ├── circuit_statistics.py
│   ├── driver_performance.py
│   ├── model_dashboard.py
│   ├── data_preprocessor.py
│   ├── model_trainer.py
│   └── __init__.py
├── data/
│   └── raw_data.csv
├── models/
│   ├── race_winner_model.pkl
│   ├── circuit_encoder.pkl
│   └── driver_encoder.pkl
├── cache/                      # FastF1 cache folder
├── streamlit_app.py            # Main frontend entrypoint
├── requirements.txt
└── README.md                   
```

---

### ⚙️ Setup & Installation

#### 🔐 Requirements
- Python 3.8+
- Internet connection (to fetch race data via FastF1)

#### 📦 Install Dependencies

```bash
pip install -r requirements.txt
```

#### ✅ Required Python Packages
- `fastf1`
- `pandas`
- `scikit-learn`
- `seaborn`
- `matplotlib`
- `joblib`
- `streamlit`

---

### 🏁 How To Run the Project

#### Step 1: Fetch fresh F1 data
```bash
python app/data_fetcher.py
```

#### Step 2: Train or retrain the ML model
```bash
python -m app.model_trainer
```

#### Step 3: Launch Streamlit dashboard
```bash
streamlit run streamlit_app.py
```

---

### 🎉 Example GIF Reactions (Live UI)
| Finish | Emotion | Preview |
|--------|---------|---------|
| 1st    | 🏆 Victory | Driver celebrates |
| 2–10   | 😐 Neutral | Driver focus mode |
| 11+    | 😩 Sad     | Driver upset |

---

### 👨‍💻 Author
Built Nishit R Kirani — Computer Science, BNM Institute of Technology 
