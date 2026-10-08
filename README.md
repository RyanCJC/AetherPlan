# AetherPlan

AetherPlan is an AI-powered travel planning platform that generates personalized trip itineraries using agentic planning, live travel data, and interactive trip editing. It combines a React front end with a Python-powered AI planner to help travelers explore destinations, compare options, and refine a trip in real time.

## Overview

This repository contains the full travel-planning experience in two parts:

- `Altas_FE/` — React + TypeScript + Vite front end for itinerary viewing, maps, trip editing, and chat-driven planning
- `Altas_hackathon/` — Python agent layer using LangChain / LangGraph with Gemini and travel APIs for itinerary generation and route planning

The app is designed for multi-day trip planning, including flights, accommodations, activities, dining, and day-by-day route optimization.

## Key Features

- AI-assisted itinerary generation from natural language prompts
- Multi-day trip scheduling and timeline editing
- Flight, hotel, and activity recommendations
- Budget-aware planning and trip customization
- Interactive map-based destination exploration
- Trip adjustments via chat and modal-based editing flows
- Travel planning aligned to destination type, travel vibe, and user preferences

## Tech Stack

### Frontend
- React 19
- TypeScript
- Vite
- Leaflet / React Leaflet
- Tailwind CSS
- Lucide icons and motion UI

### Backend / Agent Layer
- Python 3
- LangChain Core
- LangGraph
- Google Gemini
- Google Maps / Places APIs
- Travel search and route integration modules

## Repository Structure

```text
AetherPlan/
├── README.md
├── Altas_FE/
│   ├── src/
│   ├── package.json
│   ├── vite.config.ts
│   ├── tsconfig.json
│   └── .env.example
├── Altas_hackathon/
│   ├── agent.py
│   ├── itineraryPlanner.py
│   ├── tools.py
│   ├── schemas.py
│   ├── requirements.txt
│   └── .env
└── .gitignore
```

## Getting Started

### 1. Frontend setup

```bash
cd Altas_FE
npm install
npm run dev
```

This starts the app in development mode on port `3000`.

### 2. Backend / AI planner setup

```bash
cd Altas_hackathon
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Create a `.env` file in `Altas_hackathon/` and add the required API keys, including values such as:

- `GOOGLE_MAPS_API_KEY`
- `GEMINI_API_KEY`
- `ATLAS_CLIENT_ID`
- `ATLAS_CLIENT_SECRET`
- any additional travel or service keys required by the plugin modules

Then run the planner agent:

```bash
python agent.py
```

## Typical Workflow

1. User enters a travel request in the frontend or agent input flow.
2. The Python agent retrieves relevant destinations, flights, lodging, and activities.
3. The generated itinerary is structured and returned to the UI.
4. Users can review, modify, and refine the plan through chat and timeline controls.
5. The final trip is structured around dates, trip preferences, and route optimization.

## Notes

- The frontend expects the backend service to be available locally when using the travel planning and itinerary APIs.
- API keys and secret values should never be committed to source control.
- The `Altas_hackathon/.env` file is intended for local development only.

## License

This project is provided for internal or educational use unless otherwise specified by the repository owner.
