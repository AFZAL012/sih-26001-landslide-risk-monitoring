
---

# `backend/README.md`

```md
# Landslide Risk Monitoring — Backend

FastAPI backend for the SIH26001 Landslide Early-Warning and Risk Monitoring System.

The backend integrates Google Earth Engine environmental datasets with the existing machine-learning risk prediction pipeline and exposes the resulting information through REST API endpoints consumed by the React frontend.

## Features

- FastAPI REST API
- Google Earth Engine integration
- Location-based environmental data retrieval
- Landslide risk prediction using the existing ML model
- Rainfall monitoring
- Soil-moisture monitoring
- Elevation retrieval
- Slope calculation
- Snow-cover retrieval
- Risk score and risk-level generation
- Model confidence
- Risk-factor extraction
- Dashboard summary API
- CORS support for the React frontend

## Tech Stack

- Python
- FastAPI
- Uvicorn
- Google Earth Engine Python API
- XGBoost / Random Forest
- Joblib
- NumPy
- Pandas
- Python-dotenv

## Project Structure

```text
backend/
├── api/
│   ├── __init__.py
│   ├── routes.py
│   └── schemas.py
│
├── data/
│   └── historical_landslide.csv
│
├── ml/
│   ├── models/
│   ├── prediction/
│   └── features/
│
├── services/
│   ├── __init__.py
│   ├── cdse_auth.py
│   ├── earth_engine.py
│   ├── elevation.py
│   ├── rainfall.py
│   ├── risk.py
│   ├── slope.py
│   ├── snow.py
│   └── soil_moisture.py
│
├── .env
├── .env.example
├── app.py
├── requirements.txt
└── README.md

                 ┌─────────────────────┐
                 │   React Frontend    │
                 │   localhost:5173    │
                 └──────────┬──────────┘
                            │
                            │ REST API
                            ▼
                 ┌─────────────────────┐
                 │     FastAPI         │
                 │   localhost:8000    │
                 └──────────┬──────────┘
                            │
             ┌──────────────┼──────────────┐
             │              │              │
             ▼              ▼              ▼
      Google Earth      ML Pipeline    Dashboard Data
         Engine
             │              │
             │              ▼
             │       Risk Prediction
             │
             ├── Rainfall
             ├── Soil Moisture
             ├── Elevation
             ├── Slope
             └── Snow Cover

The backend is responsible for:

1. Receiving dashboard requests
2. Initializing Google Earth Engine
3. Retrieving environmental observations
4. Preparing ML features
5. Running landslide-risk prediction
6. Returning structured JSON
