# Landslide Risk Monitoring Dashboard — Frontend

A React + TypeScript dashboard for monitoring landslide risk across the North Eastern Region of India.

The frontend provides an interactive map, live risk indicators, environmental parameters, infrastructure impact information, evacuation status, emergency support units, and risk summaries.

## Features

- Interactive landslide-risk map using Leaflet
- Location-based risk markers
- Risk levels:
  - LOW
  - MEDIUM
  - HIGH
  - CRITICAL
  - UNKNOWN
- Live risk data from the FastAPI backend
- Environmental indicators:
  - Rainfall
  - Soil moisture
  - Slope
  - Elevation
  - Snow cover
- Risk score and model confidence
- Risk-factor information for monitored locations
- Infrastructure damage summary
- Evacuation and shelter-capacity information
- Emergency support-unit availability
- Automatic dashboard data refresh
- Responsive dashboard interface
- Charts and visualizations using Recharts

## Tech Stack

- React
- TypeScript
- Vite
- React Leaflet
- Leaflet
- Recharts
- CSS

## Project Structure

```text
frontend/
├── src/
│   ├── App.tsx
│   ├── main.tsx
│   └── styles.css
├── index.html
├── package.json
├── package-lock.json
├── tsconfig.json
└── vite.config.ts
