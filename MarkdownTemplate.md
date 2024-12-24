# IoT Web Application Documentation

## Table of Contents
- [IoT Web Application Documentation](#iot-web-application-documentation)
  - [Table of Contents](#table-of-contents)
  - [Executive Summary](#executive-summary)
    - [Purpose](#purpose)
    - [Scope](#scope)
    - [Audience](#audience)
  - [System Overview](#system-overview)
    - [Problem Statement](#problem-statement)
    - [Solution Highlights](#solution-highlights)
  - [Architecture Overview](#architecture-overview)
    - [Logical Architecture](#logical-architecture)
    - [Components Description](#components-description)
  - [Detailed Component Design](#detailed-component-design)
    - [IoT Devices](#iot-devices)
    - [Azure IoT Hub](#azure-iot-hub)
    - [Azure Functions](#azure-functions)
    - [SignalR Service](#signalr-service)
    - [Web Application](#web-application)
  - [Data Flow](#data-flow)
    - [End-to-End Data Flow](#end-to-end-data-flow)

---

## Executive Summary
### Purpose
Describe the purpose of the IoT web application and its key objectives.

### Scope
Define the scope of the solution, including primary features and target audience.

### Audience
Specify who this document is for (e.g., developers, architects, stakeholders).

## System Overview
### Problem Statement
What challenges does the application solve?

### Solution Highlights
Provide a high-level description of how the solution addresses these challenges:
- Real-time updates with **SignalR**.
- Device integration via **Azure IoT Hub**.
- Serverless backend using **Azure Functions**.

## Architecture Overview
### Logical Architecture
Describe the high-level architecture of the application.

![Logical Architecture](./images/logical-architecture.png)

### Components Description
- **IoT Devices**: Edge devices sending telemetry data.
- **Azure IoT Hub**: Manages device communication.
- **Azure Functions**: Processes data and triggers real-time updates.
- **SignalR Service**: Enables real-time updates to the web app.
- **Web Application**: User-facing dashboard for monitoring and control.

## Detailed Component Design
### IoT Devices
- Protocols: MQTT, AMQP, or HTTP.
- Data format: JSON.

### Azure IoT Hub
- Device provisioning and authentication.
- Message routing and telemetry ingestion.

### Azure Functions
- Trigger types: IoT Hub events, HTTP requests.
- Input/Output bindings: Event Hub.

### SignalR Service
- Real-time broadcasting.
- Scaling and connection limits.

### Web Application
- Frontend: React or Angular.
- Integration: REST APIs and SignalR.

## Data Flow
### End-to-End Data Flow
Assurez-vous que l'option "File Name Extensions" est activée dans votre système d'exploitation.(Ctrl+Shift+P puis tapez "Preview")