# Solution — Data Centres

## Key Analytics Priorities (from VA training reference)
- Sterile-zone protection
- Cabinet-row / corridor intrusion policies
- Person/vehicle restriction enforcement
- **Very low false alarm rate is the top priority** — because the environment is controlled/predictable, a **hybrid (rules + AI verification)** architecture is usually most effective
- **Value metric:** low false alarms + strict restricted-zone monitoring compliance

# 🏢 Data Center Security & Infrastructure Knowledge Base

> Master repository for designing secure, reliable, and highly available Data Centers. This document contains infrastructure recommendations, security solutions, operational efficiency improvements, integrations, automation workflows, and technology references for data center projects.

---

# 1. Data Center Areas

- Main Entrance
- Reception
- Security Checkpoint
- Visitor Waiting Area
- Mantrap
- Access Corridor
- Server Hall
- Rack Rows (Hot Aisle)
- Rack Rows (Cold Aisle)
- Network Room
- Core Switch Room
- Meet-Me Room (MMR)
- NOC / SOC
- Command Center
- UPS Room
- Battery Room
- Generator Room
- Transformer Yard
- HVAC / CRAC Area
- Electrical Room
- Fire Control Room
- Loading Bay
- Storage Room
- Spare Parts Room
- Office Area
- Parking
- Perimeter

---

# 2. Infrastructure Design

## 2.1 Camera Design

### Main Entrance

- Camera Type : 4MP AI Dome Camera
- Mounting Height : 3–3.5 m
- Lens : Motorized Varifocal
- Frame Rate : 25 FPS
- WDR : ≥140 dB
- IR Distance : ≥40 m
- Compression : H.265
- Analytics : Face Capture, People Counting, Intrusion
- Streams : Main + Sub + Metadata

---

### Reception

- Camera Type : 4MP Dome
- Analytics : Face Capture, Visitor Monitoring

---

### Security Checkpoint

- Camera Type : 5MP Dome
- Analytics :
    - Face Recognition
    - Queue Monitoring
    - Weapon Detection
    - Tailgating Detection

---

### Mantrap

- Camera Type : 5MP AI Dome
- Analytics :
    - Face Verification
    - Tailgating
    - Occupancy Detection

---

### Server Hall

- Camera Type : 4MP Dome
- Analytics :
    - Intrusion
    - Unauthorized Access
    - Person Detection
    - Smoke Detection

---

### Rack Rows

- Camera Type : Mini Dome
- Analytics :
    - Rack Door Monitoring
    - Unauthorized Presence

---

### UPS Room

- Camera Type : Bullet
- Analytics :
    - Smoke
    - Fire
    - Water Leakage

---

### Generator Area

- Camera Type : Bullet
- Analytics :
    - Intrusion
    - Fire
    - PPE Compliance

---

### Parking

#### Entry

- Camera Type : ANPR Camera
- Resolution : 4MP
- FPS : 50
- Analytics : License Plate Recognition

---

#### Parking Area

- Camera Type : Bullet Camera
- Analytics :
    - Vehicle Counting
    - Parking Occupancy

---

### Perimeter

- Camera Type : PTZ + Thermal + Bullet
- Analytics :
    - Intrusion
    - Fence Climbing
    - Loitering
    - Person Detection

---

## 2.2 Storage Design

- Continuous Recording
- Event Recording
- AI Metadata Recording

Storage

- Enterprise HDD
- Enterprise SSD
- NVMe

RAID

- RAID 5
- RAID 6
- RAID 10

Retention

- 30 / 60 / 90 / 180 Days

---

## 2.3 Server Design

- Recording Server
- AI Analytics Server
- VMS Server
- Database Server
- Access Control Server
- PSIM Server
- Backup Server
- Failover Server

General Recommendations

- Enterprise Dual CPU Server
- ECC RAM
- Redundant PSU
- Hot Swappable Drives
- GPU for AI
- Virtualization Ready
- High Availability

---

## 2.4 Network Design

- Layer 2 Switch
- Layer 3 Core
- Fiber Backbone
- 10G / 25G / 40G / 100G Backbone
- PoE+
- VLAN
- QoS
- SNMP
- RSTP
- LACP
- Redundant Core
- Dual Fiber Ring

---

## 2.5 General Design Guidelines

(To be added)

- Storage Calculation
- GPU Sizing
- CPU Sizing
- Rack Sizing
- Cooling Calculation
- Bandwidth Calculation
- Power Calculation
- UPS Calculation
- Redundancy Design

---

# 3. Security Solutions

## Video Management System (VMS)

### Possible Solutions

- Live Monitoring
- Playback
- Health Monitoring
- Smart Search
- Evidence Export
- Multi-site Management
- Video Wall

### Integrations

- PSIM
- AI Analytics
- Access Control
- Fire Alarm
- BMS

### Automated Workflows

- Camera Offline → Health Alert
- Camera Tampering → Alarm
- Smart Search → Incident Investigation

### Leading Companies

- Milestone
- Genetec
- Network Optix
- Digifort
- Qognify

---

## Face Recognition

### Possible Solutions

- Employee Authentication
- Visitor Verification
- Watchlist Detection
- Contractor Verification
- Dual Authentication

### Leading Companies

- NEC
- Corsight
- Herta
- AnyVision

---

## Access Control

### Possible Solutions

- Card Access
- Fingerprint
- Face Recognition
- Iris Recognition
- Multi-factor Authentication
- Mantrap Control
- Rack Access
- Cabinet Lock Monitoring

### Leading Companies

- HID
- Gallagher
- LenelS2
- Suprema

---

## Visitor Management

### Possible Solutions

- Visitor Registration
- QR Pass
- Self Check-in
- Contractor Management
- NDA Management
- Escort Management

### Leading Companies

- Envoy
- HID
- Honeywell

---

## AI Video Analytics

### Possible Solutions

- Intrusion Detection
- Loitering
- Weapon Detection
- Fire Detection
- Smoke Detection
- Tailgating
- Crowd Detection
- Slip & Fall
- Running Detection
- Violence Detection
- PPE Detection
- Object Left Behind
- Object Removed
- Rack Door Open Detection

### Leading Companies

- BriefCam
- Scylla
- Ipsotek
- Vaxtor
- AxxonSoft

---

## Intrusion Detection

### Possible Solutions

- PIR
- Fence Sensors
- Fiber Optic Fence Detection
- Microwave Barrier
- Beam Sensors
- Radar
- LiDAR

---

## Perimeter Protection

### Possible Solutions

- Thermal Cameras
- PTZ Auto Tracking
- Radar
- LiDAR
- Fiber Fence Detection
- Drone Detection

---

## ANPR

### Possible Solutions

- Employee Vehicle
- Visitor Vehicle
- Truck Verification
- Parking Management

---

## PSIM / Command Center

### Possible Solutions

- Alarm Management
- Incident Management
- SOP Automation
- GIS Mapping
- Dashboard
- Video Wall

---

# 4. Safety Solutions

- Fire Detection
- Smoke Detection
- Aspirating Smoke Detection (VESDA)
- Gas Suppression (FM-200, Novec 1230, Inert Gas)
- Water Leakage Detection
- Temperature Monitoring
- Humidity Monitoring
- Battery Monitoring
- Generator Monitoring
- UPS Monitoring
- Fuel Monitoring
- Emergency Lighting
- Public Address / Voice Evacuation

(Add integrations, workflows, and leading companies under each.)

---

# 5. Operational Efficiency

- DCIM (Data Center Infrastructure Management)
- Rack Occupancy
- Rack Capacity Monitoring
- Power Usage Monitoring
- Cooling Optimization
- Asset Tracking (RFID/BLE)
- Predictive Maintenance
- Energy Analytics
- Environmental Analytics
- Staff Productivity
- Maintenance Scheduling
- Spare Inventory Monitoring

---

# 6. Common Integrations

- BMS
- DCIM
- Fire Alarm Panel
- HVAC / CRAC
- UPS
- Generator
- ATS
- PDU
- EMS
- SCADA
- PLC
- Access Control
- LDAP / Active Directory
- SIEM
- ITSM (ServiceNow)
- Email
- SMS
- IP Speakers
- LiDAR
- Radar
- Drone Detection

---

# 7. Reference Notes

## Design Best Practices

(To be added)

---

## Lessons Learned

(To be added)

---

## Common Customer Requirements

(To be added)

---

## Useful RFP Clauses

(To be added)

---

## Calculation References

(To be added)

- Storage Calculator
- CPU Sizing
- GPU Sizing
- Rack Space
- Cooling
- Power
- UPS
- Network Throughput
- Fiber Design
