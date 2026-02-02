# 🚐 Smart Minibus — MVP

Smart Minibus is a web-based simulation of a **Demand-Responsive Transport (DRT)** system designed for high-density cities.

It bridges the gap between traditional fixed-route buses and on-demand ride-hailing services by introducing a **dynamic, algorithm-driven corridor model**.

This repository contains the **MVP (v0.3)** implementation: a **Single Page Application (SPA)** that simulates the full ecosystem interaction between **passengers, drivers, and a central dispatch system**.

---

## 🎯 Problem

Public transport in dense urban areas often faces structural inefficiencies:

- **Rigid Routes**  
  Buses stop at fixed locations even when no one is boarding or alighting.

- **Information Asymmetry**  
  Passengers lack visibility into seat availability and precise arrival times.

- **High Costs**  
  Point-to-point ride-hailing services (e.g., Uber) are too expensive for daily commuting.

- **Underutilization**  
  Vehicles frequently run empty during off-peak hours or along inefficient fixed paths.

There is a clear absence of a **“middle-ground” solution** that combines the efficiency of mass transit with the flexibility of on-demand transport.

---

## 💡 Solution

Smart Minibus implements a **Dynamic Corridor Model**.

Vehicles operate within a semi-fixed main road corridor while dynamically adjusting **stops, routing, and scheduling** based on real-time passenger demand.

Key concepts include:

- **Virtual Stops**  
  Physical bus stops are replaced with digital, demand-based stopping points.

- **Dynamic Scheduling**  
  Routes are recalculated instantly as new ride requests enter the system.

- **Unified Platform**  
  Passenger demand is directly translated into driver instructions through a central system brain.

---

## 🚀 Current MVP (v0.3)

**Scenario:** 🇭🇰 Hong Kong — Nathan Road Corridor  
**Target Users:** Passengers, Drivers, Fleet Operators  
**Format:** Static HTML + Vanilla JavaScript + Leaflet Maps  
**Deployment:** GitHub Pages (Static Demo)

### Core Features

- **Multi-Role Simulation**  
  Switch between Passenger (x3), Driver, and System Admin views.

- **Dynamic Routing Logic**  
  Vehicles skip stops with no demand and divert only when necessary.

- **Real-Time Feedback**  
  Live ETA updates and explicit `STOP / SKIP` driver instructions.

- **System Visualization**  
  Real-time logs display the internal decision-making of the routing algorithm.

---

## 🔄 Simulation Logic

1. **Request**  
   Passengers (Amy, Ben, Cat) select pickup and drop-off points via the Passenger App.

2. **Dispatch**  
   The System Brain receives the request and evaluates the vehicle’s current position.

3. **Optimization**  
   If the stop lies ahead and within the corridor, it is dynamically inserted into the route queue.

4. **Execution**  
   The Driver App receives a visual `STOP` command; otherwise, the vehicle defaults to `SKIP` for efficiency.

This entire feedback loop runs **fully in-browser**, powered by a custom JavaScript simulation engine.

---

## 🧠 Design Decisions

- **Corridor Mode (vs. Free-Roam)**  
  A semi-fixed corridor ensures high-frequency service suitable for mass transit, avoiding the inefficiency and unpredictability of unrestricted routing.

- **Client-Side Simulation**  
  All logic is handled via an in-memory state object, enabling instant feedback and rapid iteration without backend complexity.

- **Role-Based UI Architecture**  
  Separating Passenger, Driver, and Admin views validates usability across all system stakeholders.

- **Map-Centric Interface**  
  Leaflet.js serves as the core interaction layer, emphasizing spatial awareness as a first-class design principle.

---

## 🛣️ Roadmap

### v1.0 (Planned)

- **Real-Time Database**  
  Firebase integration for true multi-user, multi-device simulation.

- **Persistent Data**  
  Trip history and user preference storage.

- **Mobile Optimization**  
  Progressive Web App (PWA) support for a native-like mobile experience.

### Future Directions

- **Real Routing APIs**  
  Integration with Mapbox or OSRM for traffic-aware, turn-by-turn navigation.

- **Multi-Vehicle Fleet Dispatch**  
  Intelligent assignment across 5+ vehicles.

- **Dynamic Pricing Models**  
  Fare adjustments based on demand density and time-of-day patterns.

---

## 👤 Author

**Kei Chon Sio (Vasco)**  
Year 2 Student, University of Toronto  
Interests: Data Analytics, SQL, Python

📧 Email: keichonsio1114@gmail.com  
🌐 GitHub: https://github.com/vascosio1114

---

## 📜 License

This project is licensed under the **MIT License**.

Smart Minibus is an experimental MVP created for learning, exploration, and future expansion.
