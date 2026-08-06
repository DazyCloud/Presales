# Solution — Factory

## Key Detections / Analytics
- Smoke and fire
- Workers without helmet (missing PPE)
- Unauthorized entry
- Intrusion detection
- Theft prevention (object removal detection)
- Restricted area monitoring
- **If oil/gas or hazardous industrial site:** thermal/IR support is particularly relevant (night, heat sources, low-visibility conditions dominate); flame & smoke detection often faster via imaging than traditional sensors
- **Industrial (general):** dynamic safety zones around machines/robots/forklifts/AGVs/AMRs (LiDAR option), conveyor monitoring, pallet profiling, PLC/SCADA/BMS integration

# 🏭 Factory / Manufacturing Plant Security & Operational Solutions Knowledge Base

> Master repository for designing secure, safe, and operationally efficient manufacturing plants, warehouses, process industries, and industrial facilities.

---

# 1. Factory Areas

## External Areas

- Main Entrance
- Exit Gate
- Security Cabin
- Visitor Parking
- Employee Parking
- Truck Parking
- Loading Dock
- Unloading Dock
- Weighbridge
- Perimeter Fence
- Utility Area

---

## Production Areas

- Production Floor
- Assembly Line
- CNC Area
- Robotic Cell
- Conveyor Line
- Packaging Line
- Finished Goods Area
- Raw Material Storage
- Workstations
- Quality Inspection Area
- Maintenance Workshop

---

## Warehouse

- Receiving Area
- Dispatch Area
- Storage Racks
- Cold Storage
- Loading Bays
- Forklift Lanes

---

## Utility Areas

- Electrical Room
- Transformer Yard
- DG Room
- Compressor Room
- Boiler Room
- HVAC Plant
- Water Treatment Plant

---

## Critical Areas

- Control Room
- Server Room
- PLC Room
- SCADA Room
- Chemical Storage
- Fuel Storage
- Gas Storage
- Hazardous Material Area

---

## Office Areas

- Reception
- Office
- Meeting Rooms
- Cafeteria
- Locker Room

---

# 2. Infrastructure Design

## 2.1 Camera Design

### Main Entrance

- Camera Type : 4MP AI Dome
- Mounting Height : 3–3.5 m
- Lens : Motorized Varifocal
- FPS : 25
- WDR : ≥140 dB
- IR : ≥40 m
- Analytics
    - Face Capture
    - People Counting
    - Intrusion
- Streams
    - Main
    - Sub
    - Metadata

---

### Factory Floor

- Camera Type : 4MP AI Dome
- Mounting Height : 5–8 m
- Lens : Motorized Varifocal
- FPS : 25
- WDR : ≥120 dB
- Analytics
    - PPE Detection
    - Worker Monitoring
    - Machine Monitoring
    - Unsafe Behaviour

---

### Conveyor Line

- Camera Type : 5MP AI Camera
- Analytics
    - Conveyor Monitoring
    - Jam Detection
    - Object Counting
    - Product Verification

---

### Warehouse

- Camera Type : Bullet Camera
- Mounting Height : 6–10 m
- Analytics
    - Forklift Detection
    - Rack Monitoring
    - Inventory Movement

---

### Loading Dock

- Camera Type : Bullet + ANPR
- Analytics
    - Vehicle Verification
    - Truck Loading Monitoring
    - Dock Occupancy

---

### Chemical / Hazardous Area

- Camera Type : Thermal + Bullet
- Analytics
    - Fire Detection
    - Smoke Detection
    - Thermal Hotspots
    - Hazard Detection

---

### Perimeter

- Camera Type
    - PTZ
    - Thermal
    - Long Range Bullet

Analytics

- Intrusion
- Fence Climbing
- Loitering
- Auto Tracking

---

## 2.2 Storage Design

Recording

- Continuous
- Event
- Motion
- AI Metadata

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
- SCADA Integration Server
- Backup Server
- Failover Server

General Recommendations

- Enterprise Server
- ECC RAM
- GPU for AI
- Redundant PSU
- Hot Swap Drives
- High Availability
- Virtualization Support

---

## 2.4 Network Design

- Managed Layer-2/Layer-3 Switches
- Fiber Backbone
- PoE+
- VLAN
- QoS
- SNMP
- LACP
- RSTP
- Redundant Ring
- UPS Protected Network

---

## 2.5 General Design Guidelines

(To be added)

- Storage Calculation
- GPU Sizing
- CPU Sizing
- Network Design
- Fiber Design
- Power Budget
- UPS Sizing
- Cooling
- Cyber Security

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
- SCADA
- BMS

### Automated Workflows

- Camera Offline → Alarm
- Camera Tampering → Alert
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

- Employee Attendance
- Visitor Verification
- Contractor Verification
- Restricted Area Authentication
- Shift Attendance
- Watchlist Detection

### Leading Companies

- NEC
- Corsight
- Herta
- AnyVision

---

## Access Control

### Possible Solutions

- Employee Entry
- Contractor Access
- Visitor Access
- Server Room Access
- Chemical Storage Access
- Multi-factor Authentication
- Biometric Authentication

### Leading Companies

- HID
- Gallagher
- LenelS2
- Suprema

---

## AI Video Analytics

### Worker Safety

- Helmet Detection
- Safety Vest Detection
- Gloves Detection
- Goggles Detection
- Safety Shoe Detection
- PPE Compliance
- Fall Detection
- Worker Collapse Detection
- Unsafe Behaviour
- Mobile Phone Detection
- Smoking Detection

### Fire & Hazard Detection

- Smoke Detection
- Flame Detection
- Fire Detection
- Thermal Hotspot Detection
- Overheated Equipment Detection
- Gas Leak Visualization
- Chemical Spill Detection
- Water Leakage Detection

### Security Analytics

- Intrusion Detection
- Unauthorized Entry
- Restricted Area Monitoring
- Tailgating
- Loitering
- Weapon Detection
- Fight Detection
- Perimeter Intrusion
- Fence Climbing Detection

### Asset Protection

- Object Removal Detection
- Object Left Behind
- Theft Prevention
- Tool Monitoring
- Material Tracking
- Inventory Monitoring

### Machine & Process Analytics

- Conveyor Monitoring
- Conveyor Jam Detection
- Conveyor Speed Monitoring
- Machine Running Status
- Machine Idle Detection
- Machine Door Monitoring
- Emergency Stop Monitoring
- Robot Cell Monitoring
- CNC Machine Monitoring

### Logistics Analytics

- Forklift Detection
- Forklift Speed Monitoring
- AGV Monitoring
- AMR Monitoring
- Crane Monitoring
- Loading Dock Monitoring
- Truck Monitoring
- Vehicle Counting
- Pallet Counting
- Pallet Profiling

### LiDAR Analytics

- Human-Machine Safety Zones
- Robot Safety Zones
- Forklift Collision Prevention
- AGV Collision Prevention
- 3D Occupancy Detection
- Dynamic Safety Zones
- Restricted Zone Enforcement
- Volume Measurement

### Operational Analytics

- Production Line Monitoring
- Bottleneck Detection
- Cycle Time Monitoring
- Worker Productivity
- Queue Monitoring
- Heat Maps
- Occupancy Monitoring
- People Counting

### Oil & Gas / Hazardous Sites

- Thermal Analytics
- Explosion Risk Monitoring
- Tank Farm Monitoring
- Pipeline Intrusion
- Hazardous Area Monitoring
- Offshore Monitoring

### Automated Workflows

- PPE Missing → Audio Warning + Supervisor Alert
- Worker Enters Robot Zone → Machine Slowdown / Stop
- Smoke Detected → Fire Alarm + Camera Popup + Evacuation
- Conveyor Jam → Maintenance Alert
- Forklift Speed Exceeded → Operator Alert
- Restricted Area Entry → Security Notification
- Object Removed → Theft Alarm
- Machine Overheating → Maintenance Ticket
- Worker Fall → Medical Team Notification

### Leading Companies

General Video Analytics

- BriefCam
- Scylla
- Ipsotek
- AxxonSoft
- Actuate

PPE Analytics

- viAct
- Intenseye
- Protex AI

Industrial AI

- Landing AI
- Cognex
- Siemens

Thermal Analytics

- FLIR
- Axis

LiDAR

- Ouster
- SICK
- Hesai
- Cepton

---

## Intrusion Detection

### Possible Solutions

- PIR
- Microwave Barrier
- Beam Sensors
- Fence Sensors
- Fiber Fence Detection
- Radar
- LiDAR

---

## Visitor Management

### Possible Solutions

- Visitor Registration
- QR Pass
- Contractor Management
- Escort Management

---

## ANPR

### Possible Solutions

- Employee Vehicle
- Truck Verification
- Loading Dock Access
- Parking Management
- Fleet Monitoring

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

## Perimeter Protection

### Possible Solutions

- Thermal Cameras
- Radar
- LiDAR
- PTZ Auto Tracking
- Fiber Fence Detection
- Drone Detection

---

# 4. Safety Solutions

- Fire Detection
- Smoke Detection
- Flame Detection
- Gas Detection
- Water Leakage Detection
- Emergency Evacuation
- Public Address / IPPA
- Environmental Monitoring
- Temperature Monitoring
- Humidity Monitoring
- Dust Monitoring
- Noise Monitoring
- Medical Emergency
- Emergency Shutdown Monitoring

(Add integrations, workflows, and leading companies under each.)

---

# 5. Operational Efficiency Solutions

- Production Monitoring
- OEE Monitoring
- Worker Productivity
- Machine Utilization
- Predictive Maintenance
- Asset Tracking
- Inventory Tracking
- Warehouse Optimization
- Dock Management
- Forklift Fleet Management
- Energy Monitoring
- Utility Monitoring
- Shift Analytics
- Quality Inspection AI
- Digital Twin

(Add integrations, workflows, and leading companies under each.)

---

# 6. Common Integrations

Industrial Systems

- PLC
- SCADA
- MES
- ERP
- HMI
- OPC-UA
- MQTT

Security Systems

- VMS
- PSIM
- Access Control
- Visitor Management
- ANPR

Facility Systems

- BMS
- Fire Alarm
- HVAC
- UPS
- Generator

Enterprise Systems

- Active Directory
- LDAP
- HRMS
- Email
- SMS

Advanced Systems

- LiDAR
- Radar
- Thermal Cameras
- IoT Sensors
- RFID
- BLE
- Drone Detection

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

- Storage Calculator
- CPU Sizing
- GPU Sizing
- Bandwidth Calculator
- UPS Sizing
- Fiber Design
- Camera Coverage Planning
- AI Server Sizing
