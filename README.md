# 🩺 Doctor Appointment Multi-Agent System

This project is a multi-agent system for managing doctor appointments, built using FastAPI for the backend, LangGraph for agent orchestration (supervisor pattern), and Streamlit for a user-friendly frontend. The system can answer queries about doctor availability, book, cancel, or reschedule appointments, and handle FAQs related to hospital services.

---

## Table of Contents

- [Project Structure](#project-structure)
- [Features](#features)
- [Requirements](#requirements)
- [Installation & Setup](#installation--setup)
- [Running the Application](#running-the-application)
- [Usage](#usage)
- [Notes](#notes)

---

## Project Structure

```
.
├── main.py                # FastAPI backend (API endpoints)
├── streamlit_ui.py        # Streamlit frontend UI
├── agent.py               # Multi-agent system using LangGraph (supervisor pattern)
├── requirements.txt       # Python dependencies
├── setup.py               # Project setup
├── utils/                 # Utility modules (e.g., LLM model loader)
├── toolkit/               # Toolkits for agent actions (e.g., booking, availability)
├── prompt_library/        # Prompt templates for agents
├── data_models/           # Data models for the system
├── data/                  # Data files (e.g., doctor availability)
├── notebook/              # Example notebooks and sample data
└── README.md              # Project documentation
```

---

## Features

- **Multi-Agent System:** Uses LangGraph to coordinate specialized agents (information, booking) under a supervisor pattern.
- **Doctor Appointment Management:** Check availability, book, cancel, or reschedule appointments.
- **Natural Language Queries:** Users can interact using natural language.
- **FastAPI Backend:** Provides a robust API for agent interaction.
- **Streamlit Frontend:** Simple, interactive web UI for end users.

---

## Requirements

- Python 3.10+
- All Python dependencies listed in `requirements.txt`

---

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd MediSched
   ```

2. **Create and activate a virtual environment:**
   ```bash
   conda create -p venv python=3.10 -y
   conda activate ./venv
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

---

## Running the Application

### 1. Start the FastAPI Backend

```bash
uvicorn main:app --reload --port 8003
```

### 2. Start the Streamlit Frontend

```bash
streamlit run streamlit_ui.py
```

- The Streamlit app will open in your browser (default: http://localhost:8501).
- Ensure the FastAPI backend is running on port 8003 (or update `API_URL` in `streamlit_ui.py` if you change the port).

---

## Usage

- Enter your user ID and query (e.g., "Can you check if a dentist is available tomorrow at 10 AM?") in the Streamlit UI.
- The system will process your request using the multi-agent backend and display the response.

---

## Notes

- The backend uses a supervisor pattern to route queries to specialized agents (information or booking).
- Data files (e.g., doctor availability) are located in the `data/` directory.
- Example usage and data exploration can be found in the `notebook/` directory.
- For development or extension, see `agent.py` for agent logic and `toolkit/toolkits.py` for available tools.