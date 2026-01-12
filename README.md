# PWP SPRING 2025

# PROJECT NAME: Pi Security Camera - RESTful Motion Detection

# Group information

* Student 1. Name and email
* Student 2. Name and email
* Student 3. Name and email
* Student 4. Name and email

# Project Overview

This project is a **motion-detecting security camera system** built using a **Raspberry Pi and Pi Camera**.
It detects motion, captures images, and uploads them to a **RESTful web server**, where a client application can view live and historical footage.

The project demonstrates:

* REST API design and implementation with multiple resources
* IoT integration using Raspberry Pi and Pi Camera
* Auxiliary service for automated motion detection and image uploading
* Client application for accessing and visualizing motion events and images

## Features

* Real-time motion detection using the Pi Camera
* Automatic upload of captured images to the server
* Logs motion events with timestamps and camera info
* Client application to view live or past motion events
* RESTful API exposing resources: cameras, images, motions, alerts, users
* Optional: alert notifications for motion events

## Project Architecture

```
Raspberry Pi + Pi Camera
    │
    ├─ Motion Detection
    ├─ Image Capture
    │
    ▼ POST /images, /motions, /alerts
    
REST API Server
    │
    ├─ Resources: /cameras, /images, /motions, /alerts, /users
    ├─ Database (SQLite/JSON)
    │
    ▼ GET requests
    
Client Application
    │
    ├─ View Images & Motion Events
    ├─ Manage Alerts
    └─ Configure Cameras
```

**Components:**

1. **REST API Server**: Stores cameras, images, motions, alerts, and user data
2. **Client Application**: Web or desktop interface for viewing images and motion events
3. **Auxiliary Service**: Runs on Raspberry Pi, detects motion, uploads images, triggers alerts

# Instructions (Required)

## Database
<!-- How to create and populate the database -->
*TODO: Add database setup instructions*

## API
<!-- How to run and test the API, url to the entrypoint -->
*TODO: Add API running instructions*

## Client
<!-- Instructions on how to setup and run the client -->
*TODO: Add client setup instructions*

## Auxiliary Service
<!-- Instructions on how to setup and run the axiliary service -->
*TODO: Add auxiliary service instructions*

## Deployment
<!-- Instructions on how to deploy the api in a production environment -->
*TODO: Add deployment instructions*
