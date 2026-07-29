MediSense 🩺 — AI-Powered Disease Prediction from Symptoms
A machine learning model that predicts the most likely disease based on a person's symptoms — trained on real patient data using Random Forest and Decision Tree classifiers.

📌 What is this project?
Imagine typing in your symptoms — fever, headache, fatigue — and instantly getting the most likely disease, along with a confidence score. That's exactly what this project does.
Instead of relying on hardcoded if-else rules (like "if fever + cough → flu"), this model learns patterns directly from real data. It was trained on thousands of patient records where symptoms were already linked to confirmed diseases, so it picks up on symptom combinations a human might miss.
This project is a natural extension of my earlier work on VitalCare, a rule-based symptom triage app. Where VitalCare used fixed logic, this project replaces that logic with a trained ML model — a step toward a smarter, data-driven diagnostic system.

⚙️ How does it work? (in simple terms)
The data: A dataset of ~4,920 patient records, each listing 132 possible symptoms (marked yes/no) and the disease the patient was actually diagnosed with — 41 diseases in total (like Malaria, Diabetes, Migraine, etc.)
Training the model: The model looks at thousands of these symptom-disease pairs and learns which symptom patterns tend to point to which disease — the same way a doctor builds intuition from experience, except here it's learned from data.
Two models, compared:
Decision Tree — works like a flowchart of yes/no questions leading to a diagnosis
Random Forest — builds many decision trees and lets them "vote" together, usually giving more accurate and reliable results
Prediction: Give the model a list of symptoms, and it returns:
The most likely disease
The top 3 possible diseases, each with a confidence percentage

🔍 Project Workflow
Data Collection → EDA → Preprocessing → Model Training → Evaluation → Prediction → Model Saving
Step	What Happens
1. EDA	Checked for missing data, visualized disease distribution
2. Preprocessing	Converted disease names into numbers the model can understand
3. Training	Trained both Random Forest and Decision Tree models
4. Evaluation	Measured accuracy, generated confusion matrix & classification report
5. Feature Importance	Identified which symptoms most strongly predict disease
6. Prediction Function	Built a reusable function: symptoms in → disease out
7. Model Saving	Exported the trained model for reuse in other applications
   
📊 Results
Random Forest Accuracy: 0.97
Decision Tree Accuracy: 0.95
Random Forest consistently outperforms a single Decision Tree, since it combines the predictions of many trees instead of relying on just one.

🧠 Tech Stack
Python
Pandas / NumPy — data handling
Scikit-learn — model training & evaluation
Matplotlib / Seaborn — visualization
Google Colab — development environment

🚀 How to Run
Open the notebook in Google Colab
Upload your kaggle.json API key
Run all cells top to bottom
Use the predict_disease() function with your own symptom list:
python
predict_disease(['fever', 'headache', 'nausea'])
🔗 Connection to VitalCare

This project directly builds on VitalCare, a symptom-based triage web app I built earlier using a rule-based scoring engine. This ML model is designed as a drop-in upgrade — replacing static rules with a trained model that improves as more data becomes available.

📁 Files in this Repo
File	Description
disease_prediction.ipynb	Full Colab notebook (EDA → training → evaluation)
disease_prediction_rf_model.pkl	Saved trained Random Forest model
label_encoder.pkl	Encoder to convert predictions back to disease names
symptom_columns.pkl	List of symptom columns the model expects as input
README.md	You're reading it
👤 Author

Yogesh — AIML Student Built as part of an ML coursework assignment, extended as a portfolio project.
