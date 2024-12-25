# 1. IoT Web Application Documentation

## 1.1. Table of Contents
- [1. IoT Web Application Documentation](#1-iot-web-application-documentation)
  - [1.1. Table of Contents](#11-table-of-contents)
  - [1.2. Executive Summary](#12-executive-summary)
    - [1.2.1. Purpose](#121-purpose)
    - [1.2.2. Scope](#122-scope)
    - [1.2.3. Audience](#123-audience)
  - [1.3. System Overview](#13-system-overview)
    - [1.3.1. Problem Statement](#131-problem-statement)
    - [1.3.2. Solution Highlights](#132-solution-highlights)
  - [1.4. Architecture Overview](#14-architecture-overview)
    - [1.4.1. Logical Architecture](#141-logical-architecture)
    - [1.4.2. Components Description](#142-components-description)
  - [1.5. Detailed Component Design](#15-detailed-component-design)
    - [1.5.1. IoT Devices](#151-iot-devices)
    - [1.5.2. Azure IoT Hub](#152-azure-iot-hub)
    - [1.5.3. Azure Functions](#153-azure-functions)
    - [1.5.4. SignalR Service](#154-signalr-service)
    - [1.5.5. Web Application](#155-web-application)
  - [1.6. Data Flow](#16-data-flow)
    - [1.6.1. End-to-End Data Flow](#161-end-to-end-data-flow)

---

## 1.2. Executive Summary
### 1.2.1. Purpose
The object of the IoT web application is an end-to-end IoT solution for streaming real-time data from an Arduino device to a web application built in Angular, using an Azure infrastructure.

- **Main objectives** :
  - **Real-time data transmission** : Ensure the flow of data from Arduino sensors to a web-based user interface.

  - **Robust IoT architecture** : Integration of several key components, such as Azure IoT Hub, Azure Function, SignalR for real-time communication, and an Angular web application.

  - **Technological interoperability** : Connect and manage various technologies (Arduino, Azure, C#, Typescript) within a coherent framework.

  - **Support for advanced use cases** : This infrastructure can be extended for similar IoT projects in Smart Home, Smart Building or Smart Manufacturing environments

  - **Security and reliability**: Management and protection of connection points and transmitted data.


### 1.2.2. Scope

- **In-Scope**:
  - Web app for controlling devices.
  - Signal between the Arduino simulator and the devices.
  - 1 account per home and multiple accounts authorised.
  - Idea : Reporting system (Time where device is on)
  
- **Out-of-Scope**:
  - No testing with real devices.

- **Primary features**:
  - **Real-time transmission**: Data from IoT devices (Arduino) is transferred in real time to an Angular web application via Azure SignalR.

  - **Modular, flexible architecture**: The solution is based on a robust architecture comprising :
      - **Arduino Board**: The source of collected data.
      - **Azure IoT Hub**: Managing IoT communication and data.
      - **Azure Function**: Backend data processing.
      - **C#**: Backend application development.
      - **SignalR Service**: Sending real-time updates to the frontend.
     - **Angular Web App**: A rich and interactive user interface built with Typescript.
  
   - **Azure Integration**: Leveraging Azure's advanced cloud services for data processing and solution scalability.

   - **Scalability**: Designed to handle complex systems such as smart cities, factories, and logistic hubs.

   - **Security and Change Management**: Includes endpoint management, data protection, and robust processes for handling system changes.
 
- **Target audience**:
  - **Technology and industrial companies**:
    - Companies seeking connected solutions for smart factories, logistics, and complex urban environments.
  
  - **Intelligent building owners**:
    - Managers looking to optimize energy consumption, improve security, and integrate collaborative technologies.

  - **Advanced domestic users**:
    - Those looking to integrate IoT solutions to automate and enhance their homes.
  
  - **Consultants and integrators of IoT solutions**:
    - Service providers wishing to implement or customize IoT infrastructures.

### 1.2.3. Audience
This document may be intended for different audiences, depending on their role and involvement in the project. Here's a breakdown of possible recipients:

- **Developers**
  - **Audience**: Frontend developers (Angular), backend developers (C#, Azure Functions), IoT firmware developers (Arduino).
  - **Purpose**:
    - Understand the architecture and implementation details.
    - Get specific instructions for coding, testing, and  deploying various components.
    - Debugging and troubleshooting guidance.
  
- **Solution Architects**
  - **Audience**: System and solution architects overseeing the design and integration of the IoT solution.
  - **Purpose**:
    - Evaluate the scalability, security, and reliability of the solution.
    - Ensure the architecture aligns with business objectives and technical standards.
  
- **Stakeholders/Project Managers**
  - **Audience**: Non-technical or semi-technical stakeholders, such as project managers or business analysts.
  - **Purpose**:
    - Understand the project's goals, scope, and timeline.
    - Track progress and key milestones.
    - Align technical work with business needs and customer expectations.

- **System Administrators/Operators**
   - **Audience**: IT personnel responsible for maintaining the IoT solution's infrastructure.
   - **Purpose**:
     - Ensure smooth operation, monitoring, and troubleshooting of the system.
     - Manage updates and changes.

 - **End-Users (Optional)**
    - **Audience**: If the application has a user-facing component, technical documentation might also include simplified guides for end-users or administrators.
    - **Purpose**:
      - Help users interact with the system effectively.

## 1.3. System Overview
### 1.3.1. Problem Statement
The client has outlined a clear need for an IoT application capable of addressing the following objectives:

- **Centralizing IoT Devices**:
   - Provide a solution to connect and centralize data from various IoT devices in a single interface.
   - Ensure a consolidated, real-time view of the collected information for optimized management.
  
- **Managing Connected Devices**:
    - Offer functionalities for:
      - Adding, removing, and configuring devices.
      - Monitoring device status (connectivity, battery, operational state, etc.).
      - Updating firmware and device configurations remotely.
    - Ensure secure management of devices, including authentication and encrypted communications.


### 1.3.2. Solution Highlights
High-Level Description of How the Solution Addresses the Challenges
  - **Real-Time Updates with SignalR**
    - **Challenge**: Simplify device control and provide immediate feedback on actions or status changes.
    - **Solution**:
      - Integration of SignalR enables real-time communication between the backend and the web application.
      - Users can control devices and receive status updates instantly without needing to refresh the interface.
      - Ensures a seamless user experience with live updates  for device states, such as on/off status, operational errors, or configuration changes.
  
  - **Device Integration via Azure IoT Hub**
    - **Challenge**: Centralize and manage devices while ensuring compatibility with various IoT protocols.
    - **Solution**:
      - Azure IoT Hub acts as a central hub for securely connecting, monitoring, and managing devices.
      - Provides support for diverse communication protocols like MQTT, HTTP, and AMQP, ensuring compatibility with a wide range of IoT devices.
      - Facilitates bi-directional communication between devices and the application for both monitoring and control.

  - **Serverless Backend with Azure Functions**
    - **Challenge**: Manage each device effectively while maintaining a cost-efficient, scalable infrastructure.
    - **Solution**:
      - Azure Functions provides a lightweight, serverless backend for processing device events and executing control logic.
      - Supports scalability, automatically adapting to increased loads as the number of connected devices grows.
      - Simplifies backend management by focusing on event-driven functions instead of maintaining traditional server infrastructure.
  
**How These Components Support the Solution's Strengths**:
  - **Organizing Devices by Rooms**:
    - Azure IoT Hub ensures a centralized structure, while the application’s frontend (integrated with SignalR) allows users to easily categorize and view devices by rooms.
  
  - **Managing Each Device**:
    - Azure IoT Hub enables secure registration and communication for individual devices.
    - Azure Functions processes data and commands specific to each device, ensuring fine-grained management.
  
  - **Simplifying Device Control**:
    - SignalR allows for real-time updates, ensuring users can immediately see the effects of their actions.
    - The serverless backend ensures smooth control logic execution, reducing latency and improving reliability.
  
## 1.4. Architecture Overview
### 1.4.1. Logical Architecture
**The high-level architecture of the application**.

![Logical Architecture](./images/logical-architecture.png)

  Here’s a high-level flow of how these components interact:
  - **Devices** send data to **Azure IoT Hub** via secure protocols.
  - **Azure IoT Hub** forwards data to **Azure Functions** for processing.
  - **Azure Functions** executes business logic and:
    - Updates the **database** (if applicable).
    - Sends real-time updates to the **SignalR** Service.
  - **The Angular Web App** retrieves updates from **SignalR** and interacts with **Azure Functions** for actions like managing devices or sending commands.

### 1.4.2. Components Description
High-Level Description of IoT Solution Components
- **IoT Devices (Edge Devices)**
  - **Description**:
  IoT devices, such as sensors and actuators, collect and send telemetry data (e.g., temperature, motion, or humidity) to the cloud. These devices can also receive commands from the cloud for tasks like toggling power, updating configurations, or performing specific actions.
  - **Role in the Solution**:
  Acts as the data source and point of control for real-world environments, enabling interaction with physical systems.

- **Azure IoT Hub**
  - **Description**:
  A cloud-hosted service that facilitates secure, bi-directional communication between IoT devices and the backend system. It supports various protocols (e.g., MQTT, HTTP) and ensures reliable device authentication and message delivery.
  - **Role in the Solution**:
  Central hub for managing device connectivity, data exchange, and communication with the backend.

- **Azure Functions**
  - **Description**:
  A serverless computing platform that executes event-driven code in response to triggers, such as incoming telemetry data from the IoT Hub. Azure Functions processes this data, applies business logic, and triggers additional actions like storing data in a database or sending updates.
  - **Role in the Solution**:
  Acts as the brain of the system, processing data and orchestrating the flow between components like the database, SignalR, and web app.

- **SignalR Service**
  - **Description**:
  A real-time communication service that facilitates instant updates from the backend to the web application. It allows data to be pushed directly to the user interface without needing a page refresh.
  - **Role in the Solution**:
  Ensures real-time updates for users, such as live telemetry readings, device state changes, or alert notifications.

- **Web Application**
  - **Description**:
  A user-facing dashboard, typically built using frameworks like Angular, that provides an interface for monitoring devices, viewing data, and controlling the IoT devices. It connects to the SignalR service for real-time updates and interacts with the backend for actions like retrieving historical data or sending commands.
  - **Role in the Solution**:
  Serves as the control center for users, offering an intuitive and responsive way to interact with the IoT system.


## 1.5. Detailed Component Design
### 1.5.1. IoT Devices
- Protocols: MQTT, AMQP, or HTTP.
- Data format: JSON.

### 1.5.2. Azure IoT Hub
- Device provisioning and authentication.
- Message routing and telemetry ingestion.

### 1.5.3. Azure Functions
- Trigger types: IoT Hub events, HTTP requests.
- Input/Output bindings: Event Hub.

### 1.5.4. SignalR Service
- Real-time broadcasting.
- Scaling and connection limits.

### 1.5.5. Web Application
- Frontend: React or Angular.
- Integration: REST APIs and SignalR.

## 1.6. Data Flow
### 1.6.1. End-to-End Data Flow
Assurez-vous que l'option "File Name Extensions" est activée dans votre système d'exploitation.