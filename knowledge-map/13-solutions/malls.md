# Solution — Malls

## Key Analytics Priorities (from VA training reference — Retail & Commercial)
- Suspicious shopping behavior / shoplifting indicators
- Unauthorized access to staff-only/restricted areas
- Asset protection monitoring for high-value merchandise zones
- After-hours occupancy alerts
- Shopper journey, hot-spot/dwell analysis, checkout queue control
- Privacy-first anonymous footfall counting (LiDAR option — more compliant than camera-based analytics)
- **Value metric:** loss-prevention ROI + queue management efficiency

# 🛍️ Mall & Shopping Complex Security & Operational Solutions Knowledge Base

> Master repository for designing secure, safe, and intelligent shopping malls, mixed-use commercial complexes, retail centers, and entertainment destinations.

---

# 1. Mall Areas

## Public Areas

- Main Entrance
- Main Exit
- Atrium
- Corridors
- Escalators
- Elevators
- Food Court
- Seating Areas
- Children's Play Area
- Event Area
- Waiting Area
- Information Desk
- Public Toilets

---

## Retail Areas

- Fashion Stores
- Hypermarket / Supermarket
- Electronics Store
- Jewelry Store
- Luxury Retail
- Pharmacy
- Book Store
- Cinema Multiplex
- Gaming Zone

---

## Parking

- Basement Parking
- Multi-Level Parking
- VIP Parking
- Staff Parking
- Loading / Unloading Area
- Taxi Pickup
- EV Charging Area

---

## Back-of-House

- Loading Dock
- Warehouse
- Service Corridor
- Garbage Collection Area
- Electrical Room
- HVAC Plant
- Fire Control Room
- DG Room
- UPS Room
- Server Room
- Security Control Room

---

## Administrative Areas

- Mall Management Office
- Tenant Office
- Cash Collection Room
- Meeting Rooms

---

# 2. Infrastructure Design

## 2.1 Camera Design

### Main Entrance

- Camera Type : 4MP AI Dome
- Mounting Height : 3–4 m
- Lens : Motorized Varifocal
- FPS : 25
- WDR : ≥140 dB
- IR : ≥40 m
- Analytics
    - Face Capture
    - People Counting
    - Occupancy
    - Crowd Density
- Streams
    - Main
    - Sub
    - Metadata

---

### Atrium

- Camera Type : 360° Fisheye + PTZ
- Mounting Height : Ceiling Center
- Resolution : 12MP Fisheye + 4MP PTZ
- Analytics
    - Crowd Monitoring
    - Heat Maps
    - Event Monitoring
    - Suspicious Behaviour

---

### Retail Corridor

- Camera Type : 4MP Dome
- Analytics
    - People Counting
    - Queue Monitoring
    - Loitering
    - Face Capture

---

### Food Court

- Camera Type : Dome
- Analytics
    - Occupancy
    - Queue Monitoring
    - Crowd Density
    - Table Utilization

---

### Escalator

- Camera Type : Dome
- Analytics
    - Slip & Fall Detection
    - Wrong Direction Movement
    - Crowd Monitoring

---

### Parking Entry

- Camera Type : ANPR + Overview Camera
- FPS : 50
- Analytics
    - ANPR
    - Vehicle Classification
    - Parking Entry Verification

---

### Parking Area

- Camera Type : Bullet
- Analytics
    - Parking Occupancy
    - Vehicle Search
    - Suspicious Activity

---

### Loading Dock

- Camera Type : Bullet + PTZ
- Analytics
    - Vehicle Verification
    - Loading Monitoring
    - Theft Prevention

---

### Server Room

- Camera Type : Dome
- Analytics
    - Unauthorized Entry
    - Smoke
    - Fire

---

# 2.2 Storage Design

Recording

- Continuous
- Motion
- Event
- AI Metadata

Storage

- Enterprise HDD
- Enterprise SSD

RAID

- RAID 5
- RAID 6
- RAID 10

Retention

- 30 / 60 / 90 Days

---

# 2.3 Server Design

- Recording Server
- AI Analytics Server
- VMS Server
- Database Server
- Backup Server
- Failover Server

General Recommendations

- Enterprise Server
- ECC RAM
- GPU for AI Analytics
- Redundant PSU
- Hot-Swap Drives
- High Availability

---

# 2.4 Network Design

- Layer-2 / Layer-3 Managed Switches
- Fiber Backbone
- PoE+
- VLAN
- QoS
- LACP
- RSTP
- SNMP
- UPS Protected Network

---

# 2.5 General Design Guidelines

(To be added)

- Storage Calculation
- CPU Sizing
- GPU Sizing
- Camera Coverage
- Cyber Security
- Redundancy Design

---

# 3. Security Solutions

## Video Management System (VMS)

### Possible Solutions

- Live Monitoring
- Playback
- Smart Search
- Video Wall
- Health Monitoring
- Incident Investigation
- Multi-site Monitoring

### Integrations

- PSIM
- AI Analytics
- Access Control
- Fire Alarm
- BMS
- Parking Management

### Automated Workflows

- Camera Offline → Alarm
- Camera Tampering → Alert
- Incident → Bookmark Recording

### Leading Companies

- Milestone
- Genetec
- Network Optix
- Digifort

---

## Face Recognition

### Possible Solutions

- VIP Customer Identification
- Blacklisted Person Detection
- Missing Child Detection
- Watchlist Detection
- Employee Attendance
- Contractor Verification
- Repeat Customer Analytics

### Automated Workflows

- VIP Enters → Concierge Notification
- Missing Child Match → Security Alert
- Watchlist Match → Silent Alarm

### Leading Companies

- NEC
- Corsight
- Herta
- AnyVision

---

## Access Control

### Possible Solutions

- Staff Entry
- Tenant Entry
- Server Room Access
- Cash Room Access
- Loading Dock Access
- Contractor Access
- Elevator Access
- Visitor Management

### Leading Companies

- HID
- Gallagher
- Suprema
- LenelS2

---

## AI Video Analytics

### Security Analytics

- Intrusion Detection
- Loitering Detection
- Suspicious Behaviour
- Fight Detection
- Weapon Detection
- Vandalism Detection
- Theft Detection
- Object Removal Detection
- Object Left Behind
- Tailgating Detection

### Customer Analytics

- People Counting
- Occupancy Monitoring
- Heat Maps
- Customer Flow Analysis
- Dwell Time
- Queue Monitoring
- Store Footfall
- Zone Analytics
- Peak Hour Analysis
- Repeat Visitor Analytics

### Parking Analytics

- ANPR
- Vehicle Classification
- Parking Occupancy
- Wrong Parking Detection
- Illegal Parking
- Parking Guidance

### Facility Analytics

- Smoke Detection
- Fire Detection
- Water Leakage
- Escalator Monitoring
- Elevator Monitoring
- Cleaning Verification

### Automated Workflows

- Queue > Threshold → Notify Store Manager
- Crowd Density High → Security Alert
- Fight Detected → Camera Popup + Security Dispatch
- Left Bag → Alert + Camera Bookmark
- Parking Full → Digital Sign Update
- Slip & Fall → Medical Team Notification
- Escalator Incident → Maintenance Alert

### Leading Companies

General Analytics

- BriefCam
- Scylla
- Ipsotek
- AxxonSoft
- Actuate

Parking Analytics

- Vaxtor
- Adaptive Recognition

---

## Visitor Management

### Possible Solutions

- Digital Visitor Registration
- QR Visitor Pass
- Contractor Management
- Delivery Management

---

## ANPR & Parking Management

### Possible Solutions

- Ticketless Parking
- LPR-Based Parking
- VIP Parking
- Reserved Parking
- EV Charging Integration
- Parking Guidance
- Lost Ticket Management

### Technologies

- ANPR
- RFID
- QR Code
- UHF Tags

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
- Gas Detection
- Public Address / IPPA
- Voice Evacuation
- Emergency Lighting
- Water Leakage
- Medical Emergency
- Panic Alarm
- Environmental Monitoring

(Add integrations, workflows, and leading companies.)

---

# 5. Operational Efficiency Solutions

- Footfall Analytics
- Customer Journey Analytics
- Store Performance Analytics
- Queue Management
- Occupancy Monitoring
- Energy Management
- HVAC Optimization
- Cleaning Verification
- Waste Collection Monitoring
- Predictive Maintenance
- Digital Twin
- Advertisement Effectiveness Analytics

(Add integrations, workflows, and leading companies.)

---

# 6. Common Integrations

Security Systems

- VMS
- PSIM
- Access Control
- Visitor Management
- ANPR
- AI Analytics

Building Systems

- BMS
- Fire Alarm
- HVAC
- Elevator
- Escalator
- Lighting Control
- UPS
- Generator

Business Systems

- POS
- ERP
- CRM
- Loyalty Program
- Mobile App
- Digital Signage

Advanced Technologies

- LiDAR
- Radar
- IoT Sensors
- BLE Beacons
- RFID
- Indoor Positioning
- Digital Twin

---

# 7. Reference Notes

## Design Best Practices

(To be added)

## Common Customer Requirements

(To be added)

## Lessons Learned

(To be added)

## Useful RFP Clauses

(To be added)

## Calculation References

- Camera Coverage Calculator
- Storage Calculator
- CPU/GPU Sizing
- Bandwidth Calculator
- UPS Sizing
- Parking Capacity Calculator
