# Solution — Airport

## Key Detections / Analytics
- Unattended baggage
- Crowd congestion
- Intrusion in restricted areas
- Video summarization / AI search (offline search)
- Passenger flow monitoring — check-in to boarding (LiDAR/VA)
- Queue length, wait-time estimation, density heatmaps
- Platform/airside-edge safety and trackside/restricted-zone intrusion
- **Value metric:** platform safety + investigation acceleration

# ✈️ Airport Security & Operational Solutions Knowledge Base

> Master repository for airport security, safety, passenger management, operational efficiency, infrastructure design, and system integrations.

---

# 1. Airport Areas

## Public Areas

- Main Entrance
- Departure Drop-off
- Arrival Pickup
- Forecourt
- Parking
- Taxi Area
- Bus Bay
- Public Waiting Area

---

## Terminal

- Check-in Hall
- Self Check-in Kiosk
- Baggage Drop
- Security Screening
- Immigration
- Customs
- Boarding Gates
- Arrival Hall
- Departure Hall
- Duty Free
- Retail Area
- Food Court
- Lounge
- VIP Lounge
- Medical Room
- Lost & Found
- Prayer Room
- Washrooms

---

## Airside

- Apron
- Aircraft Parking Stand
- Taxiway
- Runway
- Jet Bridge
- Ground Service Area
- Baggage Loading Area
- Fuel Farm
- Hangar
- Maintenance Area
- Air Traffic Control Building

---

## Restricted Areas

- Security Control Room
- Airport Operations Center (APOC)
- Command Center
- NOC
- SOC
- Server Room
- Electrical Room
- UPS Room
- Generator Room
- Baggage Handling System Room
- Cargo Area
- Customs Storage
- Staff Entrance
- Perimeter

---

# 2. Infrastructure Design

## 2.1 Camera Design

### Terminal Entrance

- Camera Type : 4MP AI Dome
- Mounting Height : 3–3.5 m
- Lens : Motorized Varifocal
- FPS : 25
- WDR : ≥140 dB
- IR : ≥40 m
- Analytics :
    - Face Capture
    - People Counting
    - Crowd Density
    - Intrusion
- Streams :
    - Main
    - Sub
    - Metadata

---

### Check-in Area

- Camera Type : 4MP Dome
- Analytics :
    - Queue Monitoring
    - Occupancy
    - Customer Counting

---

### Security Screening

- Camera Type : 5MP Dome
- Analytics :
    - Face Recognition
    - Queue Monitoring
    - Weapon Detection
    - Suspicious Behaviour

---

### Immigration

- Camera Type : 5MP AI Dome
- Analytics :
    - Face Recognition
    - Watchlist Detection
    - Passport Verification Support

---

### Boarding Gate

- Camera Type : Dome
- Analytics :
    - Passenger Counting
    - Boarding Verification
    - Queue Monitoring

---

### Baggage Claim

- Camera Type : Dome
- Analytics :
    - Crowd Monitoring
    - Left Luggage
    - Object Removal

---

### Apron

- Camera Type : PTZ + Bullet
- Analytics :
    - Vehicle Detection
    - Aircraft Monitoring
    - Intrusion

---

### Runway

- Camera Type : Long Range PTZ
- Thermal Camera
- Radar Integration

Analytics

- Intrusion
- Wildlife Detection
- Unauthorized Vehicle

---

### Parking

#### Entry

- Camera Type : ANPR
- FPS : 50
- Analytics :
    - Number Plate Recognition

#### Parking Area

- Camera Type : Bullet
- Analytics :
    - Parking Occupancy
    - Vehicle Counting

---

### Perimeter

- Camera Type :
    - Thermal
    - PTZ
    - Long Range Bullet

Analytics

- Intrusion
- Fence Climbing
- Loitering
- Auto Tracking

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
- PSIM Server
- Access Control Server
- Backup Server
- Failover Server

General Recommendations

- Enterprise Server
- ECC RAM
- GPU for AI
- Hot Swap Drives
- Redundant PSU
- High Availability
- Virtualization

---

## 2.4 Network Design

- Managed Layer-2/Layer-3 Switches
- Fiber Backbone
- 10G / 25G / 40G / 100G Links
- PoE+
- VLAN
- QoS
- SNMP
- RSTP
- LACP
- Redundant Ring Topology

---

## 2.5 General Design Guidelines

(To be added)

- Storage Calculation
- GPU Sizing
- CPU Sizing
- Network Calculation
- Fiber Design
- UPS Design
- Power Budget
- Cyber Security

---

# 3. Security Solutions

## Video Management System (VMS)

### Possible Solutions

- Live Monitoring
- Playback
- Smart Search
- Health Monitoring
- Multi-terminal Monitoring
- Video Wall
- Incident Investigation
- Camera Health Dashboard

### Integrations

- PSIM
- AI Analytics
- Access Control
- Fire Alarm
- BMS
- AODB
- BHS

### Automated Workflows

- Camera Offline → Alarm
- Camera Tampering → Popup
- Smart Search → Investigation

### Leading Companies

- Milestone
- Genetec
- Network Optix
- Digifort
- Qognify

---

## Face Recognition

### Possible Solutions

- Watchlist Detection
- VIP Recognition
- Immigration Assistance
- Employee Verification
- Contractor Verification
- Passenger Verification

### Leading Companies

- NEC
- Corsight
- Herta
- AnyVision

---

## Access Control

### Possible Solutions

- Staff Access
- Airside Access
- Restricted Area Access
- Vehicle Gate Access
- Multi-factor Authentication
- Biometric Authentication
- Mantrap

### Leading Companies

- HID
- Gallagher
- LenelS2
- Suprema

---

## AI Video Analytics

### Possible Solutions

#### Passenger Analytics

- Queue Monitoring
- People Counting
- Crowd Density
- Occupancy
- Heat Maps
- Passenger Flow
- Dwell Time

#### Security Analytics

- Intrusion Detection
- Loitering
- Weapon Detection
- Fight Detection
- Running Detection
- Violence Detection
- Suspicious Behaviour
- Abandoned Object
- Object Removal
- Tailgating

#### Airside Analytics

- Aircraft Stand Monitoring
- GSE Vehicle Detection
- Wildlife Detection
- Foreign Object Debris (FOD) Detection
- Runway Intrusion
- Apron Safety Monitoring

### Automated Workflows

- Queue Threshold → Open Additional Counter
- Crowd Density High → Notify Operations
- Left Baggage → Security Alert
- Runway Intrusion → ATC Alert
- Wildlife Detected → Airside Operations Alert

### Leading Companies

- BriefCam
- Ipsotek
- Scylla
- AxxonSoft
- Vaxtor

---

## Visitor Management

- Visitor Registration
- Contractor Management
- QR Pass
- Escort Management
- Temporary Access

---

## ANPR

### Possible Solutions

- Staff Parking
- Passenger Parking
- VIP Vehicle
- Taxi Management
- Cargo Vehicle
- Airside Vehicle Authorization

---

## PSIM / Command Center

### Possible Solutions

- Alarm Management
- Incident Management
- SOP Automation
- GIS Mapping
- Dashboard
- Video Wall
- Multi-terminal Operations

---

## Perimeter Protection

### Possible Solutions

- Thermal Cameras
- PTZ Auto Tracking
- Radar
- LiDAR
- Fiber Fence Detection
- Drone Detection
- Anti-drone System
- Microwave Barrier

---

## Baggage Security

### Possible Solutions

- Baggage Tracking
- Left Baggage Detection
- Object Removal Detection
- Conveyor Monitoring
- Baggage Jam Detection

---

## Cargo Security

### Possible Solutions

- Cargo Monitoring
- Seal Verification
- Container Tracking
- Loading Monitoring

---

# 4. Safety Solutions

- Fire Detection
- Smoke Detection
- Gas Detection
- Voice Evacuation (IPPA/PA)
- Emergency Lighting
- Water Leak Detection
- Weather Monitoring
- Lightning Detection
- Wildlife Hazard Monitoring
- Fuel Leak Detection
- Environmental Monitoring
- Medical Emergency Response

(Add integrations, workflows, and leading companies under each.)

---

# 5. Operational Efficiency

- Queue Management
- Passenger Flow Analytics
- Check-in Optimization
- Boarding Analytics
- Security Lane Optimization
- Immigration Wait-Time Monitoring
- Retail Footfall Analytics
- Parking Management
- Flight Information Display Integration
- Resource Allocation
- Staff Productivity
- Cleaning Verification
- Energy Management
- Predictive Maintenance
- Digital Twin

(Add integrations, workflows, and leading companies under each.)

---

# 6. Common Integrations

## Airport Systems

- AODB (Airport Operational Database)
- BHS (Baggage Handling System)
- FIDS (Flight Information Display System)
- CUTE/CUPPS
- CUSS (Self-Service Kiosks)
- E-Gates
- Boarding Systems

## Security Systems

- VMS
- PSIM
- Access Control
- FRS
- ANPR
- AI Analytics

## Facility Systems

- BMS
- HVAC
- Fire Alarm
- Elevator
- Escalator
- UPS
- Generator

## Enterprise Systems

- Active Directory
- LDAP
- HRMS
- ERP
- Email
- SMS
- WhatsApp

## Advanced Systems

- Radar
- LiDAR
- Drone Detection
- SCADA
- GIS
- IoT Sensors
- Weather Stations

---

# 7. Reference Notes

## Design Best Practices

(To be added)

## Common Airport Regulations

(To be added)

## Useful RFP Clauses

(To be added)

## Lessons Learned

(To be added)

## Calculation References

- Storage Calculator
- CPU/GPU Sizing
- Bandwidth Calculator
- Fiber Design
- UPS Sizing
- Camera Coverage Planning
- AI Server Sizing
