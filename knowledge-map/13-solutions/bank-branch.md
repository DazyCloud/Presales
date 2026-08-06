# 🏦 Bank Security & Operational Solutions Knowledge Base

> A master repository containing infrastructure design recommendations, possible security and operational solutions, integrations, automated workflows, and technology references for banking projects.

---

# 1. Bank Areas

- Branch
- ATM
- Head Office
- Strong Room / Vault
- Cash Processing Center
- Teller Counter
- Locker Area
- Parking
- Entry / Exit
- Server Room
- Customer Waiting Area
- Cash Van Loading Area
- Perimeter

---

# 2. Infrastructure Design

## 2.1 Camera Design

### Branch

#### Entrance

- Camera Type : 4MP Dome Camera
- Mounting Height : 3–3.5 m
- Lens : Motorized Varifocal (2.8–12 mm)
- Frame Rate : 25 FPS
- WDR : ≥120 dB
- IR Distance : ≥30 m
- Compression : H.265/H.265+
- Analytics : Face Capture, People Counting, Intrusion
- Streams : Main + Sub + Metadata

---

#### Teller Counter

- Camera Type : 4MP Dome Camera
- Mounting Height : 3 m
- Lens : Fixed 2.8 mm
- Frame Rate : 25 FPS
- WDR : ≥140 dB
- IR : Not Required
- Analytics : Queue Monitoring, Customer Counting

---

#### Vault Entrance

- Camera Type : 5MP Dome Camera
- Mounting Height : 3 m
- Frame Rate : 30 FPS
- WDR : ≥140 dB
- IR : ≥30 m
- Analytics : Face Recognition, Intrusion Detection

---

#### Branch Hall

- Camera Type : 360° Fisheye Camera
- Mounting Height : Ceiling Center
- Resolution : 12MP
- Frame Rate : 20 FPS
- Analytics : Occupancy, Heat Map, Crowd Density

---

### ATM
## Components
- **NVR + Camera**
- **Intrusion Detection**
- **Fire & Safety**
- **+ AI/Analytics**

## Key Integration Note
- These are integrated with a **CMS (Central Monitoring System)** for alarm monitoring and playback — **not VMS**.
- **Why not VMS:** ATMs have a limited number of cameras per site, so a full VMS is unnecessary overhead — CMS is the right fit for alarm monitoring + playback at this scale.
#### ATM Cabin

- Camera Type : 4MP Mini Dome
- Mounting Height : Ceiling
- WDR : ≥120 dB
- Frame Rate : 25 FPS
- Analytics : Face Capture, Loitering, Mask Detection

---

#### ATM Entrance

- Camera Type : Bullet Camera
- Resolution : 4MP
- IR : ≥50 m
- Analytics : Intrusion, Vehicle Detection

---

### Parking

#### Entry / Exit

- Camera Type : ANPR Camera
- Resolution : 4MP
- Frame Rate : 50 FPS
- IR : ≥50 m
- Analytics : Number Plate Recognition

---

#### Parking Area

- Camera Type : Bullet Camera
- Resolution : 4MP
- Analytics : Vehicle Counting, Parking Occupancy

---

## 2.2 Storage Design

- Recording Type
    - Continuous
    - Event
    - Motion
    - AI Triggered

- Storage Media
    - Enterprise HDD
    - Enterprise SSD (OS / Database)

- RAID Recommendation
    - RAID 5
    - RAID 6
    - RAID 10

- Retention
    - 30 / 60 / 90 / 180 Days

---

## 2.3 Server Design

- Recording Server
- AI Analytics Server
- Management Server
- Database Server
- Backup Server
- Failover Server

General Recommendations

- Enterprise Server Platform
- ECC Memory
- Redundant Power Supply
- Hardware RAID Controller
- SSD for OS
- GPU where AI analytics are used
- Virtualization support
- High Availability support

---

## 2.4 Network Design

- Layer-2 / Layer-3 Managed Switches
- PoE / PoE+
- Fiber Backbone
- Cat6/Cat6A Cabling
- VLAN Segmentation
- QoS
- STP/RSTP
- LACP
- SNMP Monitoring
- Redundant Core Switch
- UPS Protected Network

---

## 2.5 General Design Guidelines

(To be filled later)

- Bandwidth Calculations
- Storage Calculations
- GPU Sizing
- CPU Sizing
- UPS Sizing
- Rack Space
- Cooling
- Redundancy
- Cyber Security

---

# 3. Security Solutions

## Face Recognition System (FRS)

### Possible Solutions

- VIP customer identification
- Blacklisted customer detection
- Wanted person detection
- Duplicate identity alerts
- Employee attendance
- Touchless attendance
- Staff verification before vault access
- Cash van personnel verification

### Typical Integrations

- VMS
- Access Control
- Visitor Management
- HRMS
- Command & Control

### Automated Workflows

- VIP detected → Silent notification
- Blacklisted customer detected → Security alert
- Vault opened → Verify authorized personnel
- Cash van personnel verified before entry

### Leading Solution Providers

- NEC
- Corsight
- Herta
- AnyVision
- Hikvision
- iOmniscient

---

## Video Management System (VMS)

### Possible Solutions

- Live Monitoring
- Playback
- Smart Search
- Video Bookmarking
- Central Recording
- Multi-site Monitoring
- Mobile Client
- User Permission Management
- Video Wall
- Health Monitoring

### Automated Workflows

- Camera Offline → Health Alert
- Camera Tampering → Alarm
- Incident Bookmark
- Smart Search using AI Metadata

### Leading Solution Providers

- Milestone
- Genetec
- Network Optix (Nx Witness)
- Qognify
- Digifort
- AxxonSoft

---

## Access Control

### Possible Solutions

- Employee Access
- Vault Access
- Locker Access
- Server Room Access
- Anti-tailgating
- Multi-factor Authentication

### Automated Workflows

- Door Forced Open
- Door Held Open
- Tailgating
- Emergency Exit Opened
- Restricted Area Access

### Leading Solution Providers

- HID
- Gallagher
- LenelS2
- Suprema
- Honeywell

---

## AI Video Analytics

### Possible Solutions

- Loitering Detection
- Intrusion Detection
- Suspicious Behaviour
- Queue Monitoring
- People Counting
- Occupancy Monitoring
- Heat Maps
- Crowd Density
- Abandoned Object
- Object Removal
- Weapon Detection
- Fire Detection
- Smoke Detection
- Fight Detection
- Slip & Fall Detection
- Running Detection
- Violence Detection
- Mask Detection
- Mobile Phone Detection
- PPE Detection

### Automated Workflows

- Weapon Detected → Alarm + Camera Popup
- Queue Threshold Exceeded → Notify Manager
- Fire Detected → IPPA + Evacuation
- Loitering at ATM → Audio Warning
- Crowd Density High → Dashboard Alert

### Leading Solution Providers

- BriefCam
- Scylla
- Ipsotek
- Vaxtor
- AxxonSoft
- Hailo
- Actuate

---

## Intrusion Alarm

## Possible Solutions

- PIR
- Motion detector
- Glass break
- Door contact
- Window contact
- Vibration sensor
- Panic button
- Duress alarm
- Siren

### Integrations

- VMS
- PTZ Cameras
- PSIM
- Access Control
- IPPA

### Automated Workflows

- Glass break → PTZ focuses on area
- Motion after business hours → Alarm + Video popup
- Panic button → Silent alarm
- ATM loitering → Audio warning

---

# 6. Fire & Life Safety

## Possible Solutions

- Fire detection
- Smoke detection
- Gas detection
- Water leak detection
- Environmental sensors
- Voice evacuation
- Public Address
- Emergency lighting

### Integrations

- Fire Alarm Panel
- VMS
- PSIM
- Access Control
- Elevator
- HVAC
- BMS
- IP Speakers

### Automated Workflows

- Fire detected → Unlock emergency exits
- Fire alarm → Camera popup
- Smoke detected → Voice evacuation
- HVAC shutdown
- Lift recalled to ground floor
- Maintenance notification

---

# 7. AI Video Analytics

## Possible Solutions

- Loitering
- Crowd density
- Queue monitoring
- Intrusion
- Weapon detection
- Fire & Smoke
- Slip & Fall
- Violence detection
- Abandoned object
- Object removal
- Running detection
- PPE detection
- Mobile phone detection
- Sleeping person
- Wrong-way movement

### Integrations

- VMS
- PSIM
- IP Speakers
- FRS
- Access Control

### Automated Workflows

- Queue exceeds threshold
- Weapon detected
- Fire detected
- Crowd exceeds limit
- ATM loitering
- Suspicious behavior

---

# 8. Customer & Branch Analytics

## Possible Solutions

- Footfall
- Peak hour analysis
- Occupancy
- Heat maps
- Dwell time
- Wait time
- Staff utilization
- Customer demographics
- Repeat visitors

### Integrations

- BI Dashboard
- PSIM
- CRM

### Automated Workflows

- Occupancy >90%
- Peak hour staffing recommendation
- ATM queue redirection
- Daily KPI generation

---

# 9. ANPR

## Possible Solutions

- Parking management
- Cash van verification
- VIP vehicle detection
- Blacklisted vehicle detection
- Vehicle history

### Integrations

- Boom Barrier
- Gate Controller
- PSIM
- VMS

### Automated Workflows

- Cash van arrival
- Unauthorized vehicle
- Vehicle overstays
- Parking occupancy

---

# 10. Infrastructure & Building Management

## Possible Solutions

- HVAC monitoring
- UPS monitoring
- Generator monitoring
- Network monitoring
- Rack monitoring
- Power monitoring

### Integrations

- BMS
- SCADA
- PSIM
- VMS

### Automated Workflows

- UPS battery low
- Generator starts
- Network failure
- Power failure

---

# 11. Vault & Cash Management

## Possible Solutions

- Strong room monitoring
- Vault monitoring
- Cash room monitoring
- Cash drawer monitoring

### Integrations

- FRS
- Access Control
- Intrusion Alarm
- VMS
- ANPR

### Automated Workflows

- Vault opened outside schedule
- Motion inside vault
- Cash drawer left open
- Cash van verified
- Shock/vibration detected

---

# Common Third-Party Integrations

- Video Management System
- PSIM
- Access Control
- Fire Alarm Panel
- Public Address / IP Speakers
- Elevator Control
- Building Management System
- HVAC
- SCADA
- Visitor Management
- HRMS
- ERP
- Active Directory / LDAP
- Email
- SMS Gateway
- WhatsApp
- Mobile Application
- GIS
- Digital Signage
- IoT Sensors
- LiDAR
- Radar
- Thermal Cameras
- Drones
- Robotics
- Body Worn Cameras

---

# Operational Benefits

- Improved physical security
- Reduced theft
- Faster incident response
- Centralized monitoring
- Compliance
- Reduced manpower
- Better customer experience
- Predictive maintenance
- Operational efficiency
- Business intelligence
- Data-driven decisions

---

# 4. Safety Solutions

- Fire Detection
- Smoke Detection
- Gas Detection
- Water Leakage Detection
- Emergency Evacuation
- Public Address / IPPA
- Environmental Monitoring
- Panic Alarm
- Medical Emergency

(Add integrations, workflows, and leading vendors under each solution as above.)

---

# 5. Operational Efficiency Solutions

- Queue Management
- Footfall Analytics
- People Counting
- Occupancy Monitoring
- Heat Maps
- Customer Flow Analysis
- Branch Utilization
- Staff Productivity
- Wait Time Analytics
- Meeting Room Utilization
- Energy Optimization
- Predictive Maintenance

(Add integrations, workflows, and leading vendors under each solution.)

---

# 6. Common Integrations

- Fire Alarm System
- Building Management System (BMS)
- HVAC
- Elevator Control
- UPS Monitoring
- Generator Monitoring
- Access Control
- HRMS
- ERP
- Active Directory / LDAP
- Email
- SMS Gateway
- WhatsApp
- GIS
- Digital Signage
- IP Speakers / PA System
- LiDAR
- Radar
- Thermal Cameras
- IoT Sensors
- PLC / SCADA

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
- Bandwidth Calculator
- GPU Sizing
- CPU Sizing
- RAID Selection
- UPS Sizing
- Network Throughput
