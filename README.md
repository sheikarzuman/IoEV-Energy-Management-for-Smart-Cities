# IoEV Energy Management for Smart Cities

### An MQTT-Based Framework for Optimized EV Charging in Intelligent Transportation Systems

This project presents a simulation-based **Internet of Electric Vehicles
(IoEV)** framework for intelligent EV charging and energy management in
smart cities.

The system combines **IoT communication, MQTT, SUMO traffic simulation,
intelligent charging algorithms, energy optimization, and real-time
monitoring** to coordinate electric vehicles, charging stations, and the
energy grid.

------------------------------------------------------------------------

## 📌 Overview

As electric vehicle adoption increases, uncoordinated charging can
create peak demand, increase electricity costs, and cause longer waiting
times at charging stations.

This project addresses these challenges through an integrated IoEV
architecture that enables:

-   Real-time communication between EVs and charging stations
-   Intelligent EV charging scheduling
-   Dynamic electricity pricing
-   Energy-load optimization
-   EV traffic simulation
-   Renewable energy integration
-   Real-time system monitoring

The communication layer uses **MQTT's lightweight publish/subscribe
architecture** to exchange charging requests, battery information,
station availability, and electricity pricing data.

------------------------------------------------------------------------

## 🏗️ System Architecture

``` text
┌───────────────────────────────────────────────┐
│              APPLICATION LAYER               │
│                                               │
│ Energy Management │ Scheduling │ Analytics   │
│ Dynamic Pricing   │ Web Interface            │
└───────────────────────┬───────────────────────┘
                        │
                        │ MQTT
                        ▼
┌───────────────────────────────────────────────┐
│             COMMUNICATION LAYER              │
│                                               │
│ MQTT Broker │ IoT Gateway │ Network Security │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│                PHYSICAL LAYER                │
│                                               │
│ EVs │ Charging Stations │ Solar │ Grid       │
│ Sensors │ Smart Meters │ Energy Storage      │
└───────────────────────────────────────────────┘
```

The proposed architecture includes EVs, charging stations, renewable
energy sources, energy storage, roadside units, smart meters, sensors,
and an energy management system.

------------------------------------------------------------------------

## ⚡ Key Features

-   🔌 Smart EV Charging
-   📡 MQTT-based communication
-   🚦 SUMO traffic simulation
-   📊 Energy demand prediction
-   💰 Dynamic electricity pricing
-   🧠 Intelligent charging scheduling
-   ☀️ Renewable energy integration
-   🔋 Energy storage management
-   📈 Load balancing
-   🌐 IoT-based monitoring
-   🔄 Grid-to-Vehicle / Vehicle-to-Grid support
-   📱 Web-based monitoring interface

------------------------------------------------------------------------

## 🔄 System Workflow

``` text
EV
 │
 │ Charging Request
 ▼
MQTT Broker
 │
 ▼
Charging Station
 │
 ├── Station Availability
 ├── Electricity Price
 └── Charging Capacity
 │
 ▼
Energy Management System
 │
 ├── Load Prediction
 ├── Dynamic Pricing
 └── Charging Scheduling
 │
 ▼
Optimized Charging Decision
 │
 ▼
EV + Grid + Renewable Energy
```

------------------------------------------------------------------------

## 📡 MQTT Communication

MQTT is used as the communication protocol between EVs, charging
stations, and the central energy management system.

The system uses a topic-based communication structure:

``` text
smartcity/ev/{id}/status
smartcity/ev/{id}/charging_request
smartcity/chargingstation/{id}/status
smartcity/grid/price
```

Example charging request:

``` json
{
  "device_id": "EV_001",
  "timestamp": "ISO8601_datetime",
  "data": {
    "charging_power": 7.2,
    "required_energy": 25
  },
  "metadata": {
    "location": {
      "latitude": 13.0827,
      "longitude": 80.2707
    }
  }
}
```

The MQTT broker handles client authentication, topic subscriptions,
message routing, and communication between system components.

------------------------------------------------------------------------

## 🧠 Energy Management

The energy management system optimizes EV charging based on:

-   Grid conditions
-   Energy availability
-   Electricity prices
-   EV departure time
-   User price preferences
-   Charging station availability

### Load Prediction

The system uses **ARIMA (Autoregressive Integrated Moving Average)** to
forecast day-ahead charging demand using historical charging data.

### Dynamic Pricing

Electricity prices are dynamically adjusted according to the deviation
between actual and desired load profiles.

### Charging Scheduling

Charging sessions are prioritized based on:

-   User's accepted price
-   Vehicle departure time
-   Charging station type
-   Current electricity price
-   System load

------------------------------------------------------------------------

## 🚦 SUMO Simulation

**Eclipse SUMO (Simulation of Urban Mobility)** is used to simulate
traffic and EV movement within the intelligent transportation
environment.

The experimental setup combines:

``` text
SUMO
  +
MQTT Broker
  +
Energy Management System
  +
Web Interface
```

The system is evaluated under:

1.  Normal EV traffic
2.  Peak charging demand
3.  Security and privacy stress conditions

------------------------------------------------------------------------

## 📊 Results

  Metric                     Unscheduled   Basic Scheduling    Proposed System
  ----------------------- -------------- ------------------ ------------------
  Peak Load                      78.3 kW            64.2 kW        **52.1 kW**
  PAR                               3.45               2.89           **2.21**
  Energy Cost               \$342.18/day       \$263.55/day   **\$196.19/day**
  Grid Dependency                  87.3%              76.2%          **63.8%**
  Optimized Utilization            42.1%              58.7%          **79.4%**

### Key Results

-   **33.5% reduction in peak load**
-   **35.94% reduction in Peak-to-Average Ratio**
-   **42.66% reduction in energy cost**
-   **26.92% reduction in grid dependency**
-   **88.6% improvement in optimized utilization**

------------------------------------------------------------------------

## 📡 MQTT Performance

  Metric                  QoS 0       QoS 1      QoS 2
  ------------------ ---------- ----------- ----------
  Message Delivery        97.3%   **99.6%**   **100%**
  Average Latency       12.4 ms     18.7 ms    25.3 ms
  Bandwidth            4.2 KB/s    5.8 KB/s   7.1 KB/s
  CPU Usage                3.2%        4.7%       6.3%
  Memory Usage          24.5 MB     26.8 MB    29.2 MB

------------------------------------------------------------------------

## 🚘 Charging Wait Time

The proposed scheduling system achieved an average charging wait time
of:

### **12.96 minutes**

compared with:

-   52.5 minutes for unscheduled charging
-   32.46 minutes for basic scheduling

------------------------------------------------------------------------

## 🛠️ Technologies Used

### Programming

-   Python

### IoT & Communication

-   MQTT
-   Mosquitto
-   IoT Gateways

### Simulation

-   Eclipse SUMO

### Data & Prediction

-   Pandas
-   NumPy
-   ARIMA

### Energy Management

-   Dynamic Pricing
-   Charging Scheduling
-   Load Optimization
-   Energy Management Systems

### Other

-   JSON
-   Smart Grid Concepts
-   Renewable Energy Integration

------------------------------------------------------------------------

## 📁 Project Structure

``` text
IoEV-Energy-Management/
│
├── README.md
│
├── mqtt/
│   ├── broker/
│   ├── ev_client/
│   └── charging_station/
│
├── energy_management/
│   ├── load_prediction.py
│   ├── dynamic_pricing.py
│   └── charging_scheduler.py
│
├── sumo/
│   ├── network/
│   ├── routes/
│   └── simulation/
│
├── web/
│   └── dashboard/
│
├── data/
│
└── results/
    ├── energy_cost/
    ├── load_profile/
    └── charging_wait_time/
```

------------------------------------------------------------------------

## 🚀 Getting Started

### 1. Clone the repository

``` bash
git clone https://github.com/YOUR_USERNAME/IoEV-Energy-Management.git
cd IoEV-Energy-Management
```

### 2. Install dependencies

``` bash
pip install -r requirements.txt
```

### 3. Start the MQTT Broker

The implementation uses **Mosquitto** as the MQTT broker.

The experimental configuration uses port:

``` text
1884
```

### 4. Start the EV and Charging Station Clients

Configure the MQTT broker address and launch the respective clients.

### 5. Start the Energy Management System

Run the load prediction, pricing, and charging scheduling modules.

### 6. Start SUMO

Launch the SUMO traffic simulation and connect it to the IoEV system.

------------------------------------------------------------------------

## 🔮 Future Work

-   Machine-learning-based EV demand prediction
-   Advanced renewable-energy forecasting
-   Vehicle-to-Grid (V2G) integration
-   Edge computing
-   Improved communication interoperability
-   Real-world EV charging testbeds
-   Physical IoT hardware integration

------------------------------------------------------------------------

## 👨‍💻 Authors

### Sheik Arzuman S

School of Electronics Engineering\
Vellore Institute of Technology, Chennai

### Vetrivelan P

School of Electronics Engineering\
Vellore Institute of Technology, Chennai

------------------------------------------------------------------------

## 📄 Publication

**IoEV with Energy Management for ITS in Smart Cities: An MQTT-based
Framework for Optimized EV Charging**

This project combines IoEV, MQTT communication, intelligent energy
management, and SUMO-based transportation simulation to develop an
optimized EV charging framework for smart-city environments.

------------------------------------------------------------------------

## ⚠️ Disclaimer

This repository represents a simulation and research prototype. The
reported performance results are based on the experimental simulation
environment and should not be interpreted as results from a deployed
real-world charging network.

------------------------------------------------------------------------

## ⭐ Acknowledgements

Developed as an academic research project at **Vellore Institute of
Technology, Chennai**.

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
