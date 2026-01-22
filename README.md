# Smart Waiting Rooms – IoT Occupancy Monitoring System

An **IoT-based monitoring system** designed to track **seat occupancy in hospital waiting rooms** in real time.  
The system provides live visibility and basic usage insights to support **better patient flow management** and **operational efficiency** in healthcare environments.

This project demonstrates the design and implementation of an **end-to-end IoT system**, covering embedded firmware, wireless communication, cloud messaging, and dashboard visualization.

---

## Project Overview

In busy hospital waiting areas, staff often lack real-time visibility into seat availability and usage patterns.  
This project explores how low-cost IoT nodes can be used to **detect seat occupancy events**, transmit them wirelessly, and visualize the data on a centralized dashboard.

The system is built around:
- Distributed **ESP8266 sensing nodes** (one per seat)
- A centralized **bridge node**
- **ESP-NOW** for local wireless communication
- **MQTT** for cloud messaging
- A **Node-RED dashboard** for visualization

---

## System Architecture

![System Architecture](assets/images/system_architecture.avif)

### Data Flow
1. **Sensing Node** detects an occupancy event using a push-button input  
2. Event is transmitted wirelessly to the **Bridge Node** using **ESP-NOW**
3. Bridge Node publishes the event to an **MQTT broker** over Wi-Fi
4. **Node-RED** subscribes to MQTT topics and updates the dashboard in real time

---

## Hardware Components

- ESP8266 (sensing nodes)
- ESP8266 (bridge node)
- Push button (used to simulate seat occupancy)
- USB power supply
- Breadboard and jumper wires

> Note: Push buttons were used to simulate occupancy sensing.  
> The design can be extended to pressure sensors or load cells.

---

## Software & Technologies

- **Arduino IDE** – ESP8266 firmware development
- **ESP-NOW** – low-latency peer-to-peer wireless communication
- **Wi-Fi + MQTT** – message delivery to backend services
- **Node-RED** – dashboard and data flow orchestration

---
## Firmware Description

### Sensing Node
- Monitors a GPIO pin connected to a push button
- Uses internal pull-up configuration
- Sends occupancy state changes to the bridge node via ESP-NOW

### Bridge Node
- Receives messages from multiple sensing nodes
- Connects to Wi-Fi network
- Publishes events to MQTT topics for dashboard consumption

---

## Dashboard

The Node-RED dashboard provides:
- Live seat occupancy status
- Real-time event updates
- A centralized view of the waiting room state

![Dashboard_1Screenshot](assets/images/dashboard_1.avif)
![Dashboard_2Screenshot](assets/images/dashboard_2.avif)

## Limitations

- Push buttons are used instead of real occupancy sensors
- No authentication or encryption implemented (prototype-level system)
- Designed as a proof-of-concept, not a production deployment

---

## Future Improvements

- Replace push buttons with pressure or load sensors
- Add secure MQTT communication (TLS, authentication)
- Store historical data for long-term analytics
- Deploy backend services on a cloud platform
- Add alerts for overcrowding or prolonged wait times

---

## Author

**Pranjal Samant**  
Graduate Engineer – Robotics & Embedded Systems  

GitHub: https://github.com/pranjalsamant1  
LinkedIn: https://linkedin.com/in/pranjalsamant

