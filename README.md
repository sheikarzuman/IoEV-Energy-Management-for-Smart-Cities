# 🚗 IoEV Energy Management for Smart Cities

### An MQTT-Based Framework for Optimized EV Charging in Intelligent Transportation Systems

This project presents a simulation-based **Internet of Electric Vehicles (IoEV)** framework for intelligent EV charging and energy management in smart cities.

The system combines **IoT communication, MQTT, SUMO traffic simulation, intelligent charging algorithms, energy optimization, and real-time monitoring** to coordinate electric vehicles, charging stations, and the energy grid.

---

## 📌 Overview

As electric vehicle adoption increases, uncoordinated charging can create peak demand, increase electricity costs, and cause longer waiting times at charging stations.

This project addresses these challenges through an integrated IoEV architecture that enables:

- Real-time communication between EVs and charging stations
- Intelligent EV charging scheduling
- Dynamic electricity pricing
- Energy-load optimization
- EV traffic simulation
- Renewable energy integration
- Real-time system monitoring

The communication layer uses **MQTT's lightweight publish/subscribe architecture** to exchange charging requests, battery information, station availability, and electricity pricing data.

---

## 🏗️ System Architecture

The system is organized into three primary layers:

```text
┌───────────────────────────────────────────────┐
│              APPLICATION LAYER               │
│                                               │
│ Energy Management │ Scheduling │ Analytics   │
│ Dynamic Pricing   │ Web Interface             │
└───────────────────────┬───────────────────────┘
                        │
                        │ MQTT
                        ▼
┌───────────────────────────────────────────────┐
│             COMMUNICATION LAYER               │
│                                               │
│ MQTT Broker │ IoT Gateway │ Network Security │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│                PHYSICAL LAYER                 │
│                                               │
│ EVs │ Charging Stations │ Solar │ Grid        │
│ Sensors │ Smart Meters │ Energy Storage       │
└───────────────────────────────────────────────┘
