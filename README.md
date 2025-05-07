# Emergency Medical Triage

## Objective
Classify urgency of medical cases

## Possible Computational Techniques
1. Priority scoring
2. Threshold classification

## Flask UI Component
1. Vital inputs and coloured alert output

## Types of Dataset
1. Emergency medicine protocols
2. triage guidelines

## Possible Sources for Dataset
1. Hospital triage systems
2. emergency medicine journals

## Dataset URLs
1. https://www.cdc.gov/nchs/ahcd/index.htm
2. https://nemsis.org/

## Setup Instructions
17. Emergency Medical Triage
1. Flask app with vital signs and symptom inputs
2. Use priority scoring from triage protocols
3. Classify urgency levels
4. Build symptom-priority database
5. Add colour-coded alerts
6. Generate urgency output and actions
7. Include first aid steps
8. Recommend timing to seek care
9. Test with emergency scenarios



ADDED DOCUMENTATION 

 Triage Prediction System

A web-based system designed to assist healthcare professionals in determining the urgency of care for patients based on clinical data using a machine learning model.


Features

- Predicts patient triage level (Red, Yellow, Green) using vital signs and symptoms
- Gives actionable medical advice based on prediction
- Stores patient triage submissions in a database
- Clean and responsive Bootstrap-based UI
- Built with Flask, Pandas, Joblib, SQLAlchemy


How It Works

The system uses a pre-trained machine learning model (triage_model_with_encoding.joblib) that was trained on clinical datasets. It predicts the urgency of a patient's condition based on:

- Age
- Heart Rate
- Respiratory Rate
- Temperature
- Blood Pressure
- Oxygen Saturation
- Symptoms
- Pre-existing Conditions


Model Prediction Logic

   Triage Level     Description                                     Bootstrap Color 
|--------------|--------------------------------------------------|-----------------|
Red                Emergency - Seek care immediately                  danger      
Yellow             Urgent - Visit the hospital soon                   warning     
Green              Non-urgent - Can wait to visit clinic              success     

---

 Tech Stack

- Frontend: HTML, Bootstrap 5
- Backend: Flask
- Model: Trained & saved with joblib
- Database: Flask-SQLAlchemy (e.g., SQLite/MySQL/PostgreSQL)

---

Project Structure


triage-system/
│
├── web/
│   ├── __init__.py
│   ├── routes.py
│   ├── forms.py
│   ├── models.py
│   ├── templates/
│   │   └── index.html
│   ├── static/
│   │   └── styles.css
│
├── triage_model_with_encoding.joblib
├── README.md
└── run.py


Usage Instructions

1. Install Dependencies

bash
pip install flask flask-wtf flask-sqlalchemy pandas joblib


2. Run the App

bash
python run.py


3. Access the App

Visit: http://localhost:5000/


 Example Form Fields

Field                 Input Type  
|----------------------|---------------|
Age                          Integer     
Heart Rate               Integer     
Respiratory Rate     Integer     
Temperature            Float       
Blood Pressure         String      
Oxygen Saturation    Integer     
Symptom                 String (Text) 
Pre-existing             Condition String (Text) 


 Data Persistence

Each submission is saved in a database via the Triage model. Fields stored include all inputs and the predicted triage level.


 Testing & Validation

- Unit tests can be added to test form validation, model prediction pipeline, and database inserts.
- Ensure the model file matches the expected input schema.
