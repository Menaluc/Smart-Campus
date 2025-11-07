# 🏫 SmartCampus – Classroom Occupancy Detection

## 📘 Project Overview
SmartCampus is a machine learning–based system designed to detect classroom occupancy in real time using IoT environmental sensors.  
The project aims to improve energy efficiency, optimize classroom usage, and support sustainability goals by identifying whether rooms are **occupied (1)** or **unoccupied (0)** based on environmental data.

## 🎯 Objectives
- Reduce unnecessary energy consumption by automatically controlling lighting, heating, and air conditioning.  
- Improve space management by tracking classroom availability.  
- Support sustainability and Smart Campus initiatives.

## 🧠 Dataset
- **Samples:** 20,560 records collected from a single classroom.  
- **Features:** Temperature, Humidity, CO₂ concentration, Light intensity, and Humidity Ratio.  
- **Target:** Room occupancy (0 = unoccupied, 1 = occupied).  
- **Distribution:** 77% unoccupied, 23% occupied (imbalanced dataset).

## 🔍 Data Insights
- **Light intensity** was the strongest predictor — occupied rooms consistently show much higher light values.  
- **CO₂** levels rise significantly when rooms are occupied, confirming strong correlation with human presence.  
- **Temperature** slightly increases during occupancy (+1.3°C).  
- **Humidity** shows minimal correlation.  
- Combining Light + CO₂ + Temperature yields the most accurate predictions.

## 📊 Correlation Analysis
| Variable | Correlation with Occupancy |
|-----------|----------------------------|
| Light | **0.91** (Very strong) |
| CO₂ | 0.50 (Moderate-strong) |
| Temperature | 0.56 (Moderate) |
| Humidity | 0.05 (Very weak) |

## 🤖 Modeling
Two supervised learning models were applied using a 70/30 train-test split:

| Model | Accuracy | F1 Score | Notes |
|--------|-----------|-----------|-----------|
| Logistic Regression | 98.8% | 0.974 | Interpretable, fast baseline model |
| Random Forest | **99.1%** | **0.982** | Captures non-linear relationships, best overall |

✅ **Recommendation:**  
Use Random Forest for maximum performance, Logistic Regression for simplicity and interpretability.

## ⚙️ How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/SmartCampus.git
   cd SmartCampus
   
2. Install dependencies:  
   pip install -r requirements.txt
   
4. Run the notebook:
   jupyter notebook SmartCampus.ipynb

Requirements:
  pandas
  numpy
  matplotlib
  seaborn
  scikit-learn


Key Findings🔬
-Light and CO₂ are dominant predictors of occupancy.
-Random Forest achieved 99.1% accuracy, aligning with academic research.
-Results validate the UCI Occupancy Dataset and prior work by Candanedo & Feldheim (2016).
-Demonstrates the feasibility of machine learning–based smart campus systems.  

⚠️ Limitations
Data collected from a single classroom — needs broader validation.
Environmental conditions (HVAC, daylight) may affect readings.
Dataset imbalance (77% unoccupied vs. 23% occupied) required careful metric selection (Precision, Recall, F1).

🧩 Future Work
Expand to multiple classrooms and longer time periods.
Integrate with real-time IoT systems for automatic control.
Develop a web dashboard to visualize occupancy and energy savings.

👩‍💻 Team
Developed collaboratively by:
Menaku Chekol
Zohar Shalom
Shira Vainer
Trngo Abawa

Supervisor: Mayya Lihovodov
Institution: Holon Institute of Technology (HIT)


🌍 Acknowledgmen:
This project reproduces and validates findings from previous research:
Candanedo, L. M., & Feldheim, V. (2016). Accurate occupancy detection of an office room from light, temperature, humidity, and CO₂ measurements.
Energy and Buildings, 112, 28–39.

