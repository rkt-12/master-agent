# Master Agent - Your personal AI assistant

## Overview

This app is based on Python/Flask backend, React frontend, and voice notes functionality for task management, goal tracking, note-taking, and chat capabilities.
This app can be accessed at <br>
🔹 Frontend: https://frontend-prod-dot-pure-album-439502-s4.uc.r.appspot.com<br>
🔹 Backend: https://backend-prod-dot-pure-album-439502-s4.uc.r.appspot.com

## System Architecture

### Backend (Python/Flask)
- **Framework**: Flask with SQLAlchemy ORM
- **Database**: SQLite (development) / PostgreSQL (production)
- **Features**: RESTful API, CORS enabled, voice note transcription
- **Dependencies**: Flask, Flask-CORS, SQLAlchemy, SpeechRecognition, pydub

### Frontend (React)
- **Framework**: React with Vite
- **UI Library**: shadcn/ui components with Tailwind CSS
- **Features**: Responsive design, real-time chat, voice recording
- **Dependencies**: React, Tailwind CSS, Lucide icons, shadcn/ui

### Core Functionalities
1. **Chat Interface**: Natural language interaction with the Master Agent
2. **Task Management**: Create, update, delete, and track tasks with priorities and due dates
3. **Goal Tracking**: Set goals with progress tracking and target dates
4. **Note Taking**: Both text and voice notes with automatic transcription
5. **Dashboard**: Overview of all activities with statistics and recent items

## Google Cloud Platform (GCP) Deployment

This app is deployed on GCP using standard app deployment engine and cloudbuild for CI/CD deployment.
The app.yaml in both frontend and backend deploy both of them separately manually and the cloudbuild.yaml is responsible for the automatic deployment of the app whenever the code is pushed .
Below are the details for that 

### Prerequisites for GCP Deployment

#### Required GCP Services
Enable the following services in your GCP project:

```bash
# Enable required APIs
gcloud services enable compute.googleapis.com
gcloud services enable cloudbuild.googleapis.com
gcloud services enable run.googleapis.com
gcloud services enable sql-component.googleapis.com
gcloud services enable storage-component.googleapis.com
gcloud services enable appengine.googleapis.com
gcloud services enable cloudresourcemanager.googleapis.com
gcloud services enable iam.googleapis.com
```

#### Set up gcloud CLI
```bash
# Install gcloud CLI (if not already installed)
# Follow instructions at: https://cloud.google.com/sdk/docs/install

# Initialize and authenticate
gcloud init
gcloud auth login
gcloud config set project YOUR_PROJECT_ID
```

### Backend Deployment (App Engine)

1. **Create app.yaml for App Engine**

2. **Set up Cloud SQL (PostgreSQL)**

3. **Update Flask configuration**

4. **Deploy to App Engine**


### Frontend Deployment (Cloud Storage + CDN)

1. **Build the React application**

2. **Create Cloud Storage bucket**

3. **Upload built files**

4. **Update API endpoint in frontend**
   

## API Documentation

### Core Endpoints

#### Chat
- `POST /api/chat` - Send message to Master Agent

#### Tasks
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create new task
- `PUT /api/tasks/{id}` - Update task
- `DELETE /api/tasks/{id}` - Delete task

#### Goals
- `GET /api/goals` - Get all goals
- `POST /api/goals` - Create new goal
- `PUT /api/goals/{id}` - Update goal
- `DELETE /api/goals/{id}` - Delete goal

#### Notes
- `GET /api/notes` - Get all notes
- `POST /api/notes` - Create text note
- `POST /api/notes/voice` - Upload voice note
- `PUT /api/notes/{id}` - Update note
- `DELETE /api/notes/{id}` - Delete note

#### Dashboard
- `GET /api/dashboard` - Get dashboard statistics


## Conclusion


Your Master Agent system is now ready for deployment! This comprehensive system provides a solid foundation for personal productivity management with modern web technologies and cloud infrastructure.
