# Lidar — Notes

> For vertical use cases, LiDAR vs camera/radar/PIR comparison, solution packages, and limitations, see [`lidar-applications.md`](./lidar-applications.md).

## What is Lidar (working principle)
Lidar (Light Detection and Ranging) works by emitting laser pulses and measuring the time it takes for the light to reflect back — this is the **ToF (Time of Flight)** principle. The result is a **3D point cloud** — a set of 3D points representing the surfaces/objects the laser hit.

## Manufacturers
| Manufacturer | Country |
|---|---|
| Hesai | China |
| Luminar | USA |
| RoboSense | China |
| Ouster | USA |

*(add more manufacturers + country as researched — keep this column, it's useful when proposing solutions with origin/compliance constraints)*

## Hardware Architecture Types
| Type | Description | Typical Use Case |
|---|---|---|
| **Rotating (Mechanical/Digital) Lidar** | Spinning mechanism sweeps laser across a 360° field | Wide-area coverage — perimeter security, city/traffic monitoring |
| **Solid-State (Scanning) Lidar** | No moving parts, fixed field of view | Compact/embedded use — vehicle-mounted, fixed-point detection |

## Sensor Selection Criteria
When selecting a lidar sensor, evaluate:
- **Range**
- **Resolution**
- **FOV (Field of View)**
- **Line of sight** (clear, unobstructed path required)
- **Weather rating** (performance in rain/fog/dust)
- **Form factor**

## Lidar Design Considerations (Placement)
- **Sensor placement** — must have a clear line of sight to the area of interest
- **Mounting design** — height/angle for optimal coverage
- **Processing requirement** — compute needed to process point-cloud data in real time

## Spatial Intelligence — 3 Core Components
1. **Sensor Hardware** — rotating or solid-state (see architecture types above)
2. **Perception Software (Perception Layer)** — can be vendor-specific or sensor-agnostic. This layer measures the raw **3D points** and **translates raw sensor data into actionable environmental data** (e.g. object position, classification, movement).
3. **Analytics Board / Dashboard** — e.g. **LasePeco**

## SoC (Chip) Manufacturers
Companies making the chips used in these systems:
- Ambarella
- Hanwha
- Axis
- Huawei
