# Emotion-based-decision-model
ML system for emotional understanding, intensity prediction, and actionable user guidance using text + contextual signals under real-world noisy conditions.
# 🌿 Emotional Intelligence ML System

##  Overview
This project builds a machine learning system that:
- Understands user emotions from journal text  
- Predicts emotional intensity (1–5)  
- Suggests what the user should do  
- Decides when they should do it  

---

##  Dataset
The dataset includes:
- journal_text (user input)
- sleep_hours, energy_level, stress_level
- time_of_day, previous_day_mood
- ambience_type, face_emotion_hint
- emotional_state (target)
- intensity (target)

---

##  Approach

### 1. Text Processing
- Used **TF-IDF Vectorizer**
- n-gram range: (1,2)

### 2. Feature Engineering
- Combined:
  - Text features  
  - Metadata (sleep, stress, energy, etc.)

### 3. Models Used
- **RandomForestClassifier** → for emotional state  
- **RandomForestRegressor** → for intensity  

---

##  Model Evaluation

- Classification → accuracy, F1-score  
- Regression → Mean Squared Error (MSE)  

RMSE ≈ 1.4–1.5 (acceptable due to noisy data)

---

##  Decision System

Based on predictions, the system decides:

### What to do:
- box_breathing  
- journaling  
- grounding  
- deep_work  
- rest  

### When to do:
- now  
- within_15_min  
- later_today  
- tonight  

---

##  Uncertainty Handling

- Confidence = model probability  
- If confidence < 0.6 → marked as uncertain  

---

##  Example

**Input:**
"I feel very tired and stressed today"

**Output:**
- State: stressed  
- Intensity: ~4  
- Action: box_breathing  
- Time: now  

---

##  Key Points

- Handles noisy and short text  
- Uses both text and context  
- Provides actionable guidance  
- Includes uncertainty awareness  

---

##  How to Run

1. Install libraries:
   pip install pandas numpy scikit-learn
   
2. Run the model:
   
python final_model.py

3. Output file:
   
   predictions.csv
   
---

##  Author
Trishika Tiwari
