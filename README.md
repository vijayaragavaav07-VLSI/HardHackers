# 🌱 AgriSense AI

## AI-Powered Smart Agricultural Irrigation and Crop Monitoring System

> **An IoT + AI based agricultural intelligence platform for smart irrigation, real-time crop monitoring, weather-aware farming, water optimization, and intelligent crop decision support.**

---

## 🏆 Smart India Hackathon 2026

| Category                 | Details                                                      |
| ------------------------ | ------------------------------------------------------------ |
| **Event**                | Smart India Hackathon 2026                                   |
| **Problem Statement ID** | **PSH4**                                                     |
| **Problem Statement**    | **Smart Agricultural Irrigation and Crop Monitoring System** |
| **Institution**          | **RMK College of Engineering and Technology**                |
| **Department**           | **EE – VLSI(design & technoligy)**                                                |
| **Team Name**            | **HardHackers**                                              |
| **Project Name**         | **AgriSense AI**                                             |
| **Project Type**         | **Hardware + IoT + AI**                                      |

---

# 👥 Team HardHackers

### RMK College of Engineering and Technology

### Department of EE – VLSI

| No. | Team Member           | 
| --: | --------------------- |
|   1 | **Vijayaragavaa V**   |
|   2 | **Luckshana M S**     |
|   3 | **PUNUGOTI GEETHIKA** |
|   4 | **AAKASH DEVIN M S**  |
|   5 | **PAVANJE KARAN K**   |
|   6 | **SREE RANJAN R**     |

---

# 📌 Official Problem Statement

## Problem Statement ID: PSH4

### Smart Agricultural Irrigation and Crop Monitoring System

**Mini Description:**

> Develop an IoT-based agricultural system that monitors soil moisture, temperature, humidity and other environmental parameters and automatically controls irrigation according to crop requirements.

---

# 💡 Our Solution

## AgriSense AI

AgriSense AI is a **hardware-based IoT and AI agricultural intelligence system** developed to address the problem of inefficient irrigation and lack of real-time crop monitoring.

The system uses:

* ESP32
* Soil moisture sensors
* Temperature sensors
* Humidity sensors
* Water-level monitoring
* Environmental sensors
* Water pump/motor
* Relay/control system
* Firebase
* AI intelligence
* Weather data
* Web dashboard

to continuously monitor agricultural conditions and intelligently manage irrigation.

---

# 🚨 1. Problem We Are Solving

Traditional agricultural irrigation often depends on manual decisions.

A farmer may irrigate based on:

* Visual observation
* Fixed schedules
* Personal experience
* Guessing soil conditions

This can result in:

### 💧 Over-Irrigation

Excess water can lead to:

* Water wastage
* Soil degradation
* Root problems
* Increased electricity usage

### 🏜️ Under-Irrigation

Insufficient water can cause:

* Crop stress
* Reduced growth
* Reduced yield
* Crop damage

### 🌦️ Weather Uncertainty

Unexpected rain can make scheduled irrigation unnecessary.

### 🌱 Lack of Crop Intelligence

Different crops require different amounts of water depending on:

* Crop type
* Growth stage
* Soil
* Weather
* Environmental conditions

### 📡 Lack of Real-Time Monitoring

Farmers may not know the actual condition of the field when they are away from it.

---

# 🎯 2. Our Objective

AgriSense AI aims to:

1. Monitor agricultural fields in real time.
2. Measure soil moisture.
3. Monitor temperature.
4. Monitor humidity.
5. Monitor water availability.
6. Automatically control irrigation.
7. Reduce unnecessary water usage.
8. Consider crop requirements.
9. Integrate weather information.
10. Detect abnormal field conditions.
11. Provide real-time notifications.
12. Help farmers make better decisions using AI.
13. Maintain crop and irrigation history.
14. Recommend suitable crops for future cultivation.

---

# 🚀 3. What Makes AgriSense AI Different?

A conventional IoT irrigation system works like:

```text
Soil Moisture
      ↓
ESP32
      ↓
Threshold Check
      ↓
Motor ON/OFF
```

AgriSense AI extends this into:

```text
                 ┌───────────────┐
                 │  Soil Data    │
                 └───────┬───────┘
                         │
                 ┌───────▼───────┐
                 │ Environmental  │
                 │    Data        │
                 └───────┬───────┘
                         │
                 ┌───────▼───────┐
                 │ Crop Details   │
                 └───────┬───────┘
                         │
                 ┌───────▼───────┐
                 │ Weather Data   │
                 └───────┬───────┘
                         │
                 ┌───────▼───────┐
                 │ Historical     │
                 │ Farm Data      │
                 └───────┬───────┘
                         │
                  ┌──────▼──────┐
                  │  AI ENGINE  │
                  └──────┬──────┘
                         │
             ┌───────────┼───────────┐
             ▼           ▼           ▼
       Irrigation    Crop Health   Crop Advice
       Decision      Monitoring    & Planning
             │
             ▼
          ESP32
             │
             ▼
        Water Pump
```

Therefore:

> **AgriSense AI is not only an irrigation controller. It is an intelligent agricultural monitoring and decision-support system.**

---

# 🏗️ 4. System Architecture

```text
                         AGRISENSE AI
                              │
              ┌───────────────┴────────────────┐
              │                                │
              ▼                                ▼
        HARDWARE LAYER                    SOFTWARE LAYER
              │                                │
        ┌─────┴─────┐                   ┌──────┴──────┐
        │   ESP32   │                   │ Web Dashboard│
        └─────┬─────┘                   └──────┬───────┘
              │                                │
     ┌────────┼────────┐              ┌────────┼────────┐
     │        │        │              │        │        │
     ▼        ▼        ▼              ▼        ▼        ▼
   Soil     Temp     Humidity      Firebase    AI     Weather
 Sensor     Sensor    Sensor        Database   Engine    API
     │        │        │              │        │        │
     └────────┼────────┘              └────────┼────────┘
              │                                │
              ▼                                ▼
       Environmental Data              Farm Intelligence
              │                                │
              └──────────────┬─────────────────┘
                             ▼
                    Irrigation Decision
                             │
                             ▼
                       Relay / Driver
                             │
                             ▼
                         Water Pump
```

---

# 🔧 5. Hardware Architecture

AgriSense AI is primarily a **hardware-based project**.

## Main Controller

### ESP32

The ESP32 acts as the central field controller.

Responsibilities:

* Read sensors
* Process sensor data
* Control irrigation
* Connect to Wi-Fi
* Communicate with Firebase
* Report device status
* Execute local safety logic

---

# 🌡️ 6. Sensors

The system can monitor:

### Soil Moisture Sensor

Measures the moisture level of the soil.

Used for:

* Irrigation decisions
* Soil condition monitoring
* Crop stress detection

---

### Temperature Sensor

Measures:

* Ambient temperature
* Environmental changes
* Heat stress conditions

---

### Humidity Sensor

Measures:

* Relative humidity
* Environmental conditions
* Possible crop stress conditions

---

### Water-Level Sensor

Monitors available water.

Used to prevent irrigation when sufficient water is not available.

---

### Optional Sensors

The architecture can be extended with:

* Rain sensor
* Light sensor
* Soil pH sensor
* EC sensor
* NPK sensor

---

# 💧 7. Automated Irrigation

The system automatically controls a water pump.

Basic flow:

```text
Sensor Reading
      ↓
ESP32
      ↓
Check Crop Requirement
      ↓
Check Soil Moisture
      ↓
Check Environmental Conditions
      ↓
Check Weather
      ↓
Irrigation Decision
      ↓
Pump ON / OFF
```

---

# 🧠 8. Intelligent Irrigation

AgriSense AI does not rely only on a fixed soil-moisture threshold.

The irrigation decision can consider:

```text
Soil Moisture
      +
Crop Type
      +
Crop Growth Stage
      +
Temperature
      +
Humidity
      +
Rain Probability
      +
Water Availability
      +
Previous Irrigation
      ↓
Irrigation Recommendation
```

Example:

```text
Field: Field 01
Crop: Tomato

Soil Moisture: 34%
Temperature: 31°C
Humidity: 67%
Rain Probability: 78%

AI Recommendation:

DELAY IRRIGATION

Reason:
Rain is expected and current soil moisture
is sufficient for the crop.
```

---

# 🤖 9. AI Agriculture Intelligence

The AI layer provides decision support.

Major AI modules include:

### 🌱 AI Crop Recommendation

Recommends suitable crops based on:

* Soil type
* Land type
* Season
* Climate
* Water availability
* Location
* Previous crop

---

### 💧 AI Irrigation Recommendation

Analyzes:

* Soil moisture
* Crop requirements
* Weather
* Growth stage
* Water availability
* Historical irrigation

---

### 🌾 Crop Health Intelligence

Analyzes:

* Environmental conditions
* Soil conditions
* Crop stage
* Irrigation history

and generates a crop health score.

---

### 🔄 Next Crop Recommendation

After harvest, the system analyzes the previous crop and recommends a suitable next crop.

---

# 🌦️ 10. Weather Intelligence

Weather information can be integrated using a weather API.

The system can display:

* Current temperature
* Humidity
* Rain probability
* Rainfall
* Wind
* Weather condition
* Forecast

Weather information can influence irrigation decisions.

Example:

```text
Rain Probability: 82%

System Action:
Avoid unnecessary irrigation.
```

---

# 📊 11. Real-Time Monitoring Dashboard

The web dashboard provides a centralized view of the farm.

### Dashboard Parameters

```text
Soil Moisture
Temperature
Humidity
Water Level
Motor Status
ESP32 Status
Wi-Fi Status
Electricity Status
Crop Health
Weather
Alerts
```

Example:

```text
┌──────────────────────────────────────┐
│          FARM OVERVIEW               │
├──────────────────────────────────────┤
│ Soil Moisture       62%              │
│ Temperature         31.2°C           │
│ Humidity            67%              │
│ Water Level         82%              │
│ Motor               OFF              │
│ ESP32               ONLINE           │
│ Crop Health         87/100           │
└──────────────────────────────────────┘
```

---

# 👨‍🌾 12. Farmer Dashboard

The farmer can:

* Login
* View farms
* View fields
* Monitor sensors
* View crop information
* Control irrigation
* View weather
* Receive notifications
* Ask AI questions
* View crop health
* View irrigation history
* View water usage
* View recommendations

---

# 👨‍💼 13. Admin Dashboard

The admin can monitor:

* All farmers
* All farms
* All fields
* IoT devices
* Sensor health
* Irrigation systems
* Water usage
* Crop status
* Alerts
* AI recommendations

---

# 🏡 14. Multi-Farm Architecture

AgriSense AI is designed to support multiple farmers and multiple farms.

```text
ADMIN
 │
 ├── FARMER 001
 │    ├── FARM 01
 │    │    ├── FIELD 01
 │    │    └── FIELD 02
 │    │
 │    └── FARM 02
 │         ├── FIELD 01
 │         └── FIELD 02
 │
 ├── FARMER 002
 │    └── FARM 01
 │
 └── FARMER 003
      └── FARM 01
```

This architecture allows future expansion.

---

# 🌱 15. Crop Lifecycle Intelligence

One of the major features of AgriSense AI is crop lifecycle tracking.

```text
LAND
 ↓
CROP SELECTION
 ↓
PLANTING
 ↓
CROP MONITORING
 ↓
IRRIGATION
 ↓
CROP HEALTH
 ↓
WEATHER MONITORING
 ↓
HARVEST
 ↓
YIELD
 ↓
CROP HISTORY
 ↓
NEXT CROP RECOMMENDATION
```

This allows the platform to learn from previous crop cycles.

---

# 🔄 16. Crop Rotation Intelligence

The system stores previous crops.

Example:

```text
Previous Crop:
Tomato

Soil:
Red Soil

Water Availability:
Medium

Yield:
Good

Recommendation:
Groundnut / Green Gram
```

This can help farmers make better future planting decisions.

---

# 📈 17. Yield Intelligence

The system can estimate expected crop yield using:

* Crop type
* Farm area
* Crop age
* Soil condition
* Weather
* Irrigation
* Crop health
* Historical yield

Example:

```text
Expected Yield:

2.8 – 3.4 tonnes

Confidence:
Moderate
```

Predictions are presented as estimates and not guaranteed outcomes.

---

# 🦠 18. Crop Disease Detection

The future-ready AI module can analyze crop/leaf images.

Possible output:

```text
Possible Condition:
Leaf Spot

Confidence:
89%

Recommendation:
Inspect affected plants and verify the
condition before treatment.
```

The feature is designed as decision support and should not replace professional agricultural advice.

---

# 🌳 19. Root-Zone Monitoring

The platform can monitor root-zone conditions using soil information and irrigation history.

Possible states:

```text
OPTIMAL
DRY STRESS
WATERLOGGED
```

This provides more meaningful information than simply displaying soil moisture.

---

# 💦 20. Water Analytics

Track:

* Daily water consumption
* Weekly consumption
* Monthly consumption
* Water saved
* Irrigation duration
* Field-wise water usage

Example:

```text
Water Used Today: 2450 L

Water Saved:
680 L

Efficiency:
78%
```

---

# ⚡ 21. Power Failure Monitoring

The system can monitor electricity availability.

```text
🟢 POWER AVAILABLE

or

🔴 POWER FAILURE
```

During a power failure:

* Notify farmer
* Notify admin
* Store pending irrigation requirement
* Prevent unsafe operation
* Resume according to system configuration

---

# 📡 22. Sensor & Device Health

The dashboard monitors:

```text
ESP32              ONLINE
Soil Sensor        ONLINE
Temperature Sensor ONLINE
Humidity Sensor    ONLINE
Water Sensor       WARNING
```

If a sensor stops sending data:

```text
⚠ SENSOR FAILURE

Field: Field 02
Sensor: Soil Moisture
Last Update: 18 minutes ago
```

---

# 🔔 23. Notification System

Notifications include:

### Soil

* Low moisture
* Abnormal moisture

### Crop

* Crop stress
* Possible disease

### Weather

* Heavy rain
* Extreme heat

### Hardware

* ESP32 offline
* Sensor failure
* Pump failure

### Electricity

* Power failure
* Power restored

---

# ☁️ 24. Cloud Architecture

Firebase can be used for:

* Authentication
* Realtime Database
* Real-time sensor data
* User management
* Alerts
* Farm information
* Crop history

---

# 🗄️ 25. Database Structure

Suggested Firebase structure:

```text
users/
    userId/

farmers/
    farmerId/

farms/
    farmId/

fields/
    fieldId/

crops/
    cropId/

cropCycles/
    cycleId/

cropHistory/
    fieldId/

sensors/
    sensorId/

sensorData/
    fieldId/
        timestamp/

irrigation/
    fieldId/

waterAnalytics/
    fieldId/

weather/
    location/

devices/
    deviceId/

alerts/
    userId/

aiRecommendations/
    fieldId/
```

---

# 🔐 26. Security

Use:

* Firebase Authentication
* Role-based authorization
* Secure Firebase Database Rules
* Farmer-specific access
* Admin-level access

A farmer should only access authorized farms and fields.

---

# 🖥️ 27. Technology Stack

## Hardware

* ESP32
* Soil Moisture Sensor
* Temperature Sensor
* Humidity Sensor
* Water Level Sensor
* Relay Module
* Water Pump
* Additional environmental sensors

## Software

* HTML
* CSS
* JavaScript
* React.js if required

## Cloud

* Firebase
* Firebase Authentication
* Firebase Realtime Database

## AI

* AI/ML Model or AI API
* Crop Recommendation
* Irrigation Intelligence
* Crop Health
* Crop Rotation
* Yield Intelligence

## APIs

* Weather API

## Mapping

* Leaflet.js

## Simulation

* Wokwi / hardware simulation where required

---

# 🔌 28. Hardware-to-Cloud Data Flow

```text
Sensors
   ↓
ESP32
   ↓
Sensor Processing
   ↓
Wi-Fi
   ↓
Firebase Realtime Database
   ↓
Web Dashboard
   ↓
AI Analysis
   ↓
Recommendation
   ↓
Control Command
   ↓
ESP32
   ↓
Relay
   ↓
Water Pump
```

---

# 🧠 29. Edge + Cloud Intelligence

A key design principle is:

> **Do not depend completely on cloud AI for basic safety-critical control.**

The ESP32 handles local control and safety.

Cloud/AI handles:

* Advanced analysis
* Weather-aware decisions
* Crop recommendations
* Historical analysis
* Predictive intelligence

Architecture:

```text
LOCAL EDGE CONTROL
        +
CLOUD INTELLIGENCE
        =
RELIABLE SMART AGRICULTURE
```

---

# 🧪 30. Demo / Simulation Mode

For hackathon demonstrations, AgriSense AI should support simulated sensor data.

Simulate:

* Soil moisture decrease
* Temperature increase
* Humidity changes
* Rain
* Water-level changes
* Motor ON/OFF
* Power failure
* ESP32 offline
* Sensor failure

Example:

```text
Normal Condition
      ↓
Soil Moisture Decreases
      ↓
System Detects Dry Condition
      ↓
Weather API Checked
      ↓
Rain Expected
      ↓
Irrigation Delayed
      ↓
Rain Occurs
      ↓
Soil Moisture Increases
      ↓
Water Saved
```

---

# 🏆 31. SIH 2026 Demonstration Flow

The recommended hackathon demonstration:

### 1. Login

Farmer logs into AgriSense AI.

### 2. Select Farm

```text
Farm 01
```

### 3. Select Field

```text
Field 01
```

### 4. View Live Data

```text
Soil Moisture: 32%
Temperature: 31°C
Humidity: 67%
Water Level: 82%
```

### 5. Detect Dry Soil

System detects decreasing soil moisture.

### 6. Check Crop

```text
Crop:
Tomato

Growth Stage:
Flowering
```

### 7. Check Weather

```text
Rain Probability:
78%
```

### 8. AI Decision

```text
DELAY IRRIGATION
```

### 9. Rain Occurs

Soil moisture increases.

### 10. Water Saving

System records saved water.

### 11. Crop Health

Farm health score updates.

### 12. Crop History

Data is stored.

### 13. Harvest

Yield is recorded.

### 14. Next Crop

AI recommends the next suitable crop.

This demonstrates the complete intelligence cycle.

---

# 🎨 32. UI/UX Design

The AgriSense AI dashboard should be:

* Modern
* Professional
* Clean
* Responsive
* Farmer-friendly
* Data-driven
* Hackathon-ready

### Main Navigation

```text
Dashboard

Farm Management
 ├── Farms
 ├── Fields
 └── Crops

Live Monitoring
 ├── Sensors
 ├── Devices
 └── Hardware Health

Irrigation
 ├── Control
 ├── History
 └── Water Analytics

AI Intelligence
 ├── Crop Advisor
 ├── Agriculture Assistant
 ├── Crop Health
 ├── Disease Detection
 ├── Yield Intelligence
 └── Next Crop

Weather

Farm Map

Reports

Notifications

Settings
```

---

# 📱 33. Farmer-Centric Interface

The interface should avoid unnecessary technical complexity.

Instead of showing only:

```text
ADC = 2387
GPIO = 34
Firebase packet = OK
```

the farmer should see:

```text
🌱 Crop Health
GOOD

💧 Irrigation
NOT REQUIRED

🌦️ Weather
RAIN EXPECTED

⚠️ Field 02
CHECK SOIL

🤖 AI Recommendation
Delay irrigation for 6 hours.
```

Technical information can remain inside the hardware monitoring section.

---

# 📊 34. Farm Health Score

AgriSense AI can calculate an overall farm health score.

Possible parameters:

```text
Soil Health
Water Management
Crop Health
Weather Risk
Irrigation Efficiency
Sensor Reliability
```

Example:

```text
FARM HEALTH SCORE

87 / 100
```

---

# 🌍 35. Sustainability

AgriSense AI focuses on sustainable farming.

### Expected benefits:

💧 Reduce unnecessary water usage

⚡ Reduce unnecessary energy consumption

🌱 Improve crop planning

🌾 Improve crop management

📊 Improve resource utilization

🌦️ Adapt irrigation to weather

🔄 Support crop rotation

---

# 📈 36. Key Performance Indicators

The system can measure:

```text
Water Used
Water Saved
Irrigation Efficiency
Crop Health
Farm Health
Yield
Energy Usage
Sensor Reliability
Crop Success
```

---

# 🧪 37. Reliability & Data Transparency

The platform must clearly distinguish:

```text
LIVE DATA
SIMULATED DATA
ESTIMATED DATA
AI PREDICTION
```

For example:

```text
ESP32:
OFFLINE

Last Data:
10:32 AM
```

The system should never display simulated data as real sensor data.

---

# 🔮 38. Future Scope

Future versions can include:

### Advanced Sensors

* Soil pH
* EC
* NPK
* Advanced soil sensors

### AI

* Advanced disease detection
* Pest prediction
* Yield forecasting
* Crop stress prediction

### Satellite

* NDVI
* Vegetation monitoring
* Drought detection

### Drone

* Crop inspection
* Field mapping
* Disease detection

### Automation

* Automatic valves
* Automated fertigation
* Multiple irrigation zones

### Large-Scale Deployment

* Multiple villages
* Farmer communities
* Agricultural cooperatives
* Large farms
* Government agriculture programs

---

# 🏅 39. Why AgriSense AI is Suitable for PSH4

The PSH4 problem statement requires an IoT-based system that:

> Monitors soil moisture, temperature, humidity and other environmental parameters and automatically controls irrigation according to crop requirements.

AgriSense AI directly addresses these requirements through:

| PSH4 Requirement         | AgriSense AI Solution             |
| ------------------------ | --------------------------------- |
| Soil Moisture Monitoring | Soil Moisture Sensor + ESP32      |
| Temperature Monitoring   | Temperature Sensor                |
| Humidity Monitoring      | Humidity Sensor                   |
| Environmental Monitoring | Multiple IoT Sensors              |
| Automatic Irrigation     | ESP32 + Relay + Pump              |
| Crop Requirements        | Crop Intelligence                 |
| Real-Time Monitoring     | Firebase + Web Dashboard          |
| Water Optimization       | Water Analytics                   |
| Weather Awareness        | Weather Intelligence              |
| Crop Monitoring          | Crop Health Module                |
| Alerts                   | Notification System               |
| AI Enhancement           | AI Crop & Irrigation Intelligence |

---

# 🚀 40. Core Project Flow

```text
             AGRISENSE AI
                   │
                   ▼
              FARM SETUP
                   │
                   ▼
             FIELD SETUP
                   │
                   ▼
            CROP SELECTION
                   │
                   ▼
              ESP32 + IoT
                   │
                   ▼
         REAL-TIME SENSOR DATA
                   │
          ┌────────┴────────┐
          ▼                 ▼
       FIREBASE           WEATHER
          │                 │
          └────────┬────────┘
                   ▼
              AI ENGINE
                   │
       ┌───────────┼───────────┐
       ▼           ▼           ▼
  IRRIGATION   CROP HEALTH  CROP ADVISOR
       │
       ▼
     PUMP
       │
       ▼
     CROP
       │
       ▼
    HARVEST
       │
       ▼
 CROP HISTORY
       │
       ▼
 NEXT CROP AI
       │
       ▼
 NEW CROP CYCLE
```

---

# 🧠 41. Project Philosophy

AgriSense AI follows one central principle:

> ## **“Don't just automate irrigation. Understand the farm.”**

The objective is not simply to switch a motor ON or OFF.

The objective is to understand:

* What the crop needs
* What the soil needs
* What the weather indicates
* How much water is available
* What happened previously
* What the farmer should do next

---

# 🎯 42. Final Project Description

**AgriSense AI** is a hardware-based **IoT and AI-powered Smart Agricultural Irrigation and Crop Monitoring System** developed by **Team HardHackers from RMK College of Engineering and Technology, Department of EE – VLSI**, for **Smart India Hackathon 2026 Problem Statement PSH4**.

The system uses ESP32-based IoT hardware to monitor soil moisture, temperature, humidity, water availability, and other environmental parameters. It automatically manages irrigation according to crop requirements while integrating weather intelligence and AI-based decision support.

The platform extends beyond conventional irrigation automation by providing crop intelligence, crop health monitoring, water analytics, farm history, yield intelligence, and next-crop recommendations.

---

# 🏆 43. Final Vision

```text
             AGRISENSE AI

        SMART AGRICULTURE
               │
      ┌────────┼────────┐
      │        │        │
     IoT      AI     WEATHER
      │        │        │
      └────────┼────────┘
               │
        FARM INTELLIGENCE
               │
      ┌────────┼────────┐
      │        │        │
   WATER     CROP     FARM
 MANAGEMENT HEALTH  MANAGEMENT
      │        │        │
      └────────┼────────┘
               │
       BETTER FARM DECISIONS
               │
               ▼
       SUSTAINABLE FARMING
```

---

# 👨‍💻 Team

## HardHackers

### RMK College of Engineering and Technology

### Department of EE – VLSI(design & technology)

**Team Members**

1. **Vijayaragavaa V**
2. **Luckshana M S**
3. **PUNUGOTI GEETHIKA**
4. **AAKASH DEVIN M S**
5. **PAVANJE KARAN K**
6. **SREE RANJAN R**

---

# 🏁 SIH 2026

### Problem Statement

**PSH4 – Smart Agricultural Irrigation and Crop Monitoring System**

### Project

# 🌱 AgriSense AI

### Team

# ⚡ HardHackers

### Institution

# 🏫 RMK College of Engineering and Technology

### Department

# 🔬 EE – VLSI(design & technology)

---

## 🌱 AgriSense AI

> **From Smart Irrigation to Intelligent Farming.**
