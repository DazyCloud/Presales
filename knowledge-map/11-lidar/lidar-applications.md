# LiDAR — Verticals, Comparison & Solution Packages

*(Companion to `lidar-notes.md` — adds vertical use cases, technology comparison, and packaging not covered there.)*

## How LiDAR Works — ToF Formula
```
Distance = (photon travel time ÷ 2) × speed of light
```
Pipeline: Emission → Reflection → Time-of-Flight measurement → Point Cloud → AI Perception
Outputs delivered via standardized APIs (**gRPC, MQTT**) into VMS, traffic controllers, ACS, ICCC, or analytics dashboards.

## Key Differentiators
- **Direct 3D measurement** — not inferred like a 2D camera
- **Centimeter-level accuracy** — holds even at detection zone edges
- **Privacy-by-design** — captures point-cloud geometry (shape/distance/position) only, not faces or readable text

## LiDAR vs Other Sensing Technologies
| Capability | LiDAR | Camera (CCTV) | Radar | PIR/Beam |
|---|---|---|---|---|
| Data type | True 3D point cloud (X,Y,Z) | 2D image, depth inferred | Range + velocity, low spatial detail | Simple trigger |
| Accuracy | Centimeter-level, direct | Depends on lighting/angle | Coarse positioning | No measurement |
| Works in darkness | Yes — intrinsic light source | Poor without illumination | Yes | Limited |
| False alarms | Reduced >95% | High (shadows, wind, lighting) | Moderate | Very high |
| Privacy | Privacy-by-design, no PII | Captures faces/PII | Privacy-safe | Privacy-safe |
| Multi-target tracking | Up to ~1,000 simultaneous | Limited per camera FoV | Limited | None |

> **Strategic note:** LiDAR is not a camera replacement — it's a superior **complementary detection layer**. Optimal architecture pairs LiDAR (high-confidence 3D detection) with cameras/PTZ (visual verification) — this is **LiDAR-PTZ fusion** (auto-cues PTZ to lock onto and follow a target).

## Technology Stack (5 Layers)
1. **Sensor Hardware** — rotating or solid-state, selected by range/resolution/FOV/weather rating/form factor
2. **Edge Processing** — low-latency on-site point-cloud processing, reduces bandwidth, enables real-time events
3. **AI Perception Software** — detection, classification, tracking, virtual-zone logic, event generation (vendor-optimized or sensor-agnostic)
4. **Analytics & Dashboard** — people counting, smart-city analytics, in-store insights, parking, perimeter dashboards
5. **Integration Layer** — VMS, PSIM/ICCC, access control, traffic controllers, PA systems, SCADA/BMS, mobile alerting

> Vendor-optimized perception software = tightest integration with a matched sensor family. Sensor-agnostic software = flexibility mixing multiple hardware brands.

## Verticals & Use Cases

### Smart Cities & Intelligent Transportation
- **Signal actuation** — multimodal signal changes triggered by real-time demand, not fixed timers
- **VRU safety** — pedestrian/cyclist detection in 3D, walk-time extension, near-miss detection
- **Violation detection** — red-light runners, jaywalking, wrong-way, illegal turns
- **Virtual loop replacement** — ends road-cutting inductive loops; V2X broadcasts 3D safety messages to connected vehicles

### Perimeter Security & Critical Infrastructure
- 3D virtual fences, >95% fewer false alarms, 24/7 all-weather operation
- Object-size filtering (ignores animals/branches/vegetation)
- Tracks ~1,000 targets simultaneously, even behind partial obstruction
- **Application sites:** power plants, solar parks, substations, refineries, prisons, armouries, data centers, airports, ports, water utilities

### Crowd Management, Transit & Airports
- Square-meter-level crowd density tracking, sub-100ms safety alerts
- Surge/crush prevention, flow management, bottleneck detection
- Passenger flow (check-in to boarding), queue length, wait-time, density heatmaps
- Platform-edge safety, trackside intrusion, railway tunnel intrusion (distinguishes trains from humans/animals)

### Retail, Industrial & Ports
- **Retail:** shopper journey, hot-spot/dwell analysis, checkout queue control, privacy-first anonymous footfall counting
- **Industrial:** dynamic safety zones around machines/robots/forklifts/AGVs/AMRs, conveyor monitoring, pallet profiling, PLC/SCADA/BMS integration
- **Ports:** crane anti-collision (cm-level), worker detection in lifting zones, bulk material volume estimation
- **Mining/tunnels:** underground mapping, truck blind-spot detection, tunnel deformation detection, drone/robot-mounted LiDAR

## Recommended Solution Packages
| Package | Hardware | Software/Dashboard | Key Use Cases |
|---|---|---|---|
| Smart City Traffic Intelligence | Rotating digital LiDAR | ITS perception engine + edge compute + ICCC API | Multimodal counting, signal actuation, VRU safety, near-miss, V2X, digital twin |
| Crowd & Public-Space Analytics | Rotating digital LiDAR | Perception software + analytics dashboard | Crowd density, queue monitoring, occupancy alerts, dwell time, PA/PSIM integration |
| Critical Infrastructure Perimeter | Rotating / solid-state LiDAR | Perception software + PTZ + VMS | Virtual fencing, intrusion detection, sterile-zone, multi-target tracking, PTZ auto-cueing |
| Retail & Commercial Analytics | Rotating / dome LiDAR | Perception software + analytics dashboard + BI | Footfall, customer journey, heatmaps, dwell time, checkout queues, layout optimization |
| Industrial Safety & Automation | Rotating / solid-state LiDAR | Sensor-agnostic perception + PLC/SCADA | Worker safety, dynamic zones, collision avoidance, conveyor monitoring, volume measurement |

## Limitations & Design Considerations
1. **Line of sight** — must be clear; plan placement to avoid blind spots/occlusion from structures/vegetation
2. **Mounting design** — correct height/angle/coverage planning is critical; poor placement directly reduces accuracy
3. **Processing requirements** — large point-cloud volumes need adequate edge/central compute + network bandwidth
4. **Not a full replacement** — doesn't replace CCTV where visual evidence is required; must integrate with cameras

## Key Benefit Figures (Reference)
- **95%+** false alarm reduction (3D object-size filtering)
- **1,000** simultaneous targets tracked
- **360°** coverage from 1–2 sensors per intersection
- **0** PII captured (privacy-by-design, simplifies GDPR compliance)
