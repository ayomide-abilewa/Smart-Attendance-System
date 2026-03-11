# Smart Attendance System

AI-powered attendance management system for academic environments, built to support student enrollment, face-based attendance capture, lecturer session management, and report generation.

## Overview

This project combines a Flask backend, a React frontend, and OpenCV-based face recognition components to streamline classroom attendance workflows. It is designed as a practical engineering project with both software and applied AI elements.

## Key Features

- Student and lecturer authentication flows
- Course creation and class enrollment management
- Face setup and embedding generation for students
- Attendance marking from uploaded images or live capture
- Lecturer session management and attendance summaries
- CSV and PDF attendance report export
- Deployment-ready frontend and backend configuration

## Tech Stack

- Frontend: React, TypeScript, Vite, Tailwind CSS
- Backend: Flask, SQLAlchemy, SQLite/PostgreSQL
- Computer Vision: OpenCV, YuNet face detection, SFace recognition
- Deployment: Vercel for frontend, Render for backend

## System Structure

```text
frontend/   React application for students and lecturers
Backend/    Flask API, database models, CV pipeline, reporting utilities
papers/     Research references used during development
scripts/    Utility scripts for project assets and documents
```

## Core Workflow

1. Lecturers create courses and open attendance sessions.
2. Students register, enroll in courses, and complete face setup.
3. The system processes uploaded images or live camera frames.
4. Recognized students are matched against enrolled records.
5. Attendance data is stored and can be exported as CSV or PDF.

## Local Development

### Backend

1. `cd Backend`
2. `python -m venv .venv`
3. `.venv\Scripts\activate`
4. `pip install -r requirements.txt`
5. `python app.py`

The backend runs on `http://127.0.0.1:5000`.

### Frontend

1. `cd frontend`
2. `npm install`
3. `npm run dev`

The frontend runs on Vite's local development server and connects to `http://127.0.0.1:5000` by default.

## Configuration

### Backend environment variables

- `SECRET_KEY`
- `FLASK_DEBUG`
- `DATABASE_URL`
- `CORS_ORIGINS`
- `LECTURER_ACCESS_CODE`
- `COOLDOWN_MINUTES`
- `LIVENESS_ENABLED`
- `LIVENESS_REQUIRED`

### Frontend environment variables

- `VITE_API_BASE_URL`

## Reset Local Data

This project stores demo or test data locally in SQLite and generated asset folders. To reset the local state, remove:

- `ignis.db`
- `Backend/dataset/`
- `Backend/embeddings/`
- `Backend/exports/`

## Deployment

### Backend on Render

1. Create a new Render Web Service from this repository.
2. Render will detect `render.yaml`.
3. After deployment, copy the backend public URL.
4. Set `CORS_ORIGINS` to your frontend domain.

### Frontend on Vercel

1. Create a new Vercel project from this repository.
2. Set the root directory to `frontend`.
3. Use `npm run build` as the build command.
4. Use `dist` as the output directory.
5. Set `VITE_API_BASE_URL=https://<your-render-backend-url>`.

## Engineering Notes

- The project uses pre-trained OpenCV face detection and recognition models stored in `Backend/models/`.
- Attendance reporting supports both operational review and export for record-keeping.
- The current implementation is intended for academic demonstration, prototyping, and further extension.

## Roadmap

- Improve model evaluation and recognition accuracy benchmarking
- Add stronger audit trails and role-based access controls
- Expand test coverage across backend routes and frontend flows
- Add clearer demo data and walkthrough screenshots

## Repository Status

This repository is under active development as part of an engineering project focused on AI-assisted attendance automation.

