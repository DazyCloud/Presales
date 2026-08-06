# Solution — Metro

## Mandatory Security Features
**Offline search must be available across all zones.**

| Zone | Required Detection / Capability |
|---|---|
| **Ticket area** | Fight detection, offline search |
| **Passage** | Abandoned object detection, vandalism detection, fight detection, fall/slip detection, offline search |
| **Platform** | Line-crossing detection |
| **General / Exit** | Offline search |

## Offline Search — BriefCam
- **Fixed camera range:** 50 m
- **AI behavior approach:** memory-based — **no extra compute required** for the AI processing itself
- **Extra storage IS required** — for metadata used in memory/query triggers
- **How it works:** the system builds a memory of "normal" patterns (time of day, location, count) and flags **unusual behavior** — then classifies it into categories such as: fall, trespassing, loitering, etc.

# 🚇 Metro Rail Security & Operational Solutions Knowledge Base

> Master repository for designing secure, safe, and intelligent metro stations, underground stations, elevated stations, depots, and metro rail networks.

---

# 1. Metro Areas

## Public Areas

- Station Entrance
- Station Exit
- Concourse
- Ticket Counter
- Customer Care
- Waiting Area
- Retail Shops
- Food Court
- Washrooms

---

## Passenger Areas

- Automatic Fare Collection (AFC)
- Ticket Vending Machine (TVM)
- Automatic Gate (AFC Gates)
- Security Screening
- Paid Area
- Unpaid Area
- Platform
- Platform Screen Doors (PSD)
- Escalators
- Elevators

---

## Operational Areas

- Station Control Room (SCR)
- Operations Control Centre (OCC)
- Telecom Room
- UPS Room
- Server Room
- Electrical Room
- Signalling Room
- Relay Room

---

## Depot

- Depot Entry
- Stabling Yard
- Maintenance Shed
- Washing Plant
- Train Inspection Area
- Workshop
- OCC Backup

---

## Parking

- Two Wheeler Parking
- Car Parking
- Bus Bay
- Auto Stand

---

# 2. Infrastructure Design

## 2.1 Camera Design

### Station Entrance

- Camera Type : 4MP AI Dome
- FPS : 25
- WDR : ≥140 dB
- Analytics
    - Face Capture
    - People Counting
    - Crowd Density
    - Queue Monitoring

---

### AFC Gates

- Camera Type : Dome
- Analytics

- Tailgating
- Fare Evasion
- Queue Monitoring

---

### Platform

- Camera Type : Dome + PTZ

Analytics

- Crowd Density
- Passenger Counting
- Platform Occupancy
- Left Object Detection

---

### Platform Screen Doors

- Camera Type : AI Camera

Analytics

- Door Obstruction
- Passenger Near Door
- Object Trapped Detection

---

### Track Area

- Camera Type

- Thermal
- PTZ

Analytics

- Track Intrusion
- Animal Detection
- Object Detection

---

### Depot

- Camera Type

- PTZ
- Bullet

Analytics

- Vehicle Monitoring
- PPE Detection
- Worker Safety

---

# 2.2 Storage Design

- Continuous Recording
- Event Recording
- AI Metadata

Storage

- Enterprise HDD
- Enterprise SSD

Retention

- 30 / 60 / 90 Days

---

# 2.3 Server Design

- Recording Server
- AI Analytics Server
- VMS Server
- Database Server
- OCC Integration Server
- Backup Server

---

# 2.4 Network Design

- Fiber Backbone
- Ring Network
- Layer-3 Core
- PoE+
- VLAN
- QoS
- SNMP

---

# 3. Security Solutions

## Video Management System

### Possible Solutions

- Live Monitoring
- Playback
- Smart Search
- Multi-station Monitoring
- Health Monitoring
- Incident Investigation

---

## Face Recognition

### Possible Solutions

- Watchlist Detection
- Missing Person Detection
- Employee Authentication
- Contractor Verification

---

## Access Control

### Possible Solutions

- OCC Access
- SCR Access
- Depot Access
- Server Room
- Electrical Room
- PSD Maintenance Access

---

## AI Video Analytics

### Passenger Analytics

- Passenger Counting
- Crowd Density
- Queue Monitoring
- Heat Maps
- Passenger Flow
- Dwell Time
- Occupancy Monitoring

### Platform Safety

- Platform Edge Detection
- Passenger Fall Detection
- Track Intrusion
- Yellow Line Crossing
- Object Left Behind
- Object Removal

### AFC Analytics

- Tailgating Detection
- Fare Evasion
- Wrong Direction Entry
- Gate Blocking

### Security Analytics

- Intrusion
- Loitering
- Fight Detection
- Weapon Detection
- Vandalism
- Graffiti Detection
- Suspicious Behaviour

### Depot Analytics

- PPE Detection
- Worker Safety
- Forklift Detection
- Crane Monitoring
- Vehicle Tracking

### Automated Workflows

- Passenger Falls → Emergency Response
- Crowd Density High → Open Additional Gates
- AFC Tailgating → Security Alert
- Track Intrusion → OCC Alert
- Fire → PA Announcement + Evacuation

### Leading Companies

General Analytics

- BriefCam
- Scylla
- Ipsotek
- AxxonSoft

Metro Solutions

- Siemens Mobility
- Alstom
- Hitachi Rail
- Thales

---

## Passenger Information

### Possible Solutions

- Passenger Information Display (PIDS)
- Public Address (PAS)
- Emergency Announcements
- Digital Signage

---

## AFC

### Possible Solutions

- Smart Card
- QR Ticket
- NFC Ticket
- EMV Open Loop Payments
- Mobile Ticketing

---

## PSIM

### Possible Solutions

- Alarm Management
- SOP Automation
- Incident Management
- GIS
- Video Wall

---

# 4. Safety Solutions

- Fire Detection
- Smoke Detection
- Tunnel Fire Monitoring
- Platform Emergency Phones
- Public Address / IPPA
- Emergency Evacuation
- Flood Monitoring
- Air Quality Monitoring

(Add integrations, workflows, and leading companies.)

---

# 5. Operational Efficiency

- Passenger Flow Analytics
- Queue Optimization
- Platform Utilization
- AFC Throughput Analytics
- Train Headway Monitoring
- Escalator Monitoring
- Elevator Monitoring
- Cleaning Verification
- Energy Management
- Predictive Maintenance
- Digital Twin

(Add integrations, workflows, and leading companies.)

---

# 6. Common Integrations

Metro Systems

- Automatic Fare Collection (AFC)
- Passenger Information Display System (PIDS)
- Public Address System (PAS)
- Communications-Based Train Control (CBTC)
- Automatic Train Supervision (ATS)
- Operations Control Centre (OCC)
- Platform Screen Doors (PSD)
- SCADA

Security Systems

- VMS
- PSIM
- Access Control
- Face Recognition
- AI Analytics

Building Systems

- Fire Alarm
- BMS
- HVAC
- UPS
- Generator

Advanced Technologies

- LiDAR
- Thermal Cameras
- IoT Sensors
- Digital Twin
- GIS

---

# 7. Reference Notes

## Design Best Practices

(To be added)

## Metro Standards

(To be added)

## Useful RFP Clauses

(To be added)

## Lessons Learned

(To be added)

## Calculation References

- Camera Coverage
- Storage Calculator
- CPU/GPU Sizing
- Network Bandwidth
- Passenger Throughput Calculator
