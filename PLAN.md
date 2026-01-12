# Project Plan: Pi Security Camera

## 1. Project Overview
The goal is to build a RESTful security camera system where a Raspberry Pi detects motion, uploads images to a central server, and a client application allows users to view these events.

## 2. Technical Architecture

### 2.1 Backend (API)
*   **Language**: Python
*   **Framework**: FastAPI (or Flask)
*   **Role**: Handles requests from the Pi (uploading images) and the Client (retrieving images/metadata).
*   **Endpoints**:
    *   `POST /images`: Upload an image (from Pi).
    *   `GET /images`: List images (with filters).
    *   `GET /images/{id}`: Retrieve specific image.
    *   `POST /alerts`: Report a motion event.

### 2.2 Database
*   **Type**: Relational (SQL)
*   **Technology**: SQLite (dev) / PostgreSQL (prod)
*   **Schema**:
    *   `images`: id, timestamp, filename, camera_id
    *   `alerts`: id, timestamp, type, camera_id

### 2.3 Client (Frontend)
*   **Technology**: React.js (or simple HTML/JS/Bootstrap)
*   **Features**:
    *   Dashboard view of recent motion events.
    *   Image gallery.
    *   Live stream (optional/advanced).

### 2.4 Auxiliary Service (Raspberry Pi)
*   **Language**: Python
*   **Libraries**: `picamera`, `requests`, `gpiozero` (for PIR sensor).
*   **Logic**:
    1.  Monitor PIR sensor.
    2.  On motion -> Capture image.
    3.  `POST` image to API.

### 2.5 Deployment
*   **Containerization**: Docker & Docker Compose.
*   **Hosting**: Cloud VM (AWS/Azure/GCP) or local server.

---

## 3. Development Phases

### Phase 1: Setup & Design
*   [ ] Define detailed API specification (OpenAPI/Swagger).
*   [ ] Initialize Git repository structure.
*   [ ] Set up development environment.

### Phase 2: Backend Development (API)
*   [ ] Implement database models.
*   [ ] Create API endpoints for image upload/retrieval.
*   [ ] Implement storage logic (save files to disk/S3).
*   [ ] Write unit tests for API.

### Phase 3: Auxiliary Service (Pi)
*   [ ] Write Python script for motion detection.
*   [ ] Implement API integration (sending images).
*   [ ] Test hardware integration.

### Phase 4: Frontend Development (Client)
*   [ ] Create UI for viewing events.
*   [ ] Connect Frontend to API.
*   [ ] Implement auto-refresh or WebSocket for real-time updates.

### Phase 5: Deployment & Documentation
*   [ ] Containerize API and Frontend (Docker).
*   [ ] Write Makefiles or scripts for easy running.
*   [ ] Complete README documentation (HOWTOs).
*   [ ] Verify "Production" deployment steps.

---

## 4. Directory Structure (Proposed)

```
/
├── api/                # Backend code
│   ├── main.py
│   ├── models/
│   ├── routers/
│   └── Dockerfile
├── client/             # Frontend code
│   ├── src/
│   ├── public/
│   └── Dockerfile
├── auxiliary/          # Pi scripts
│   ├── camera_client.py
│   └── requirements.txt
├── docker-compose.yml
├── README.md
├── PLAN.md
└── meetings.md
```
