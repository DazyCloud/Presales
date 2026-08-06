# ANPR — Overview

> For camera selection, hardware sizing, components, challenges, and performance evaluation, see [`anpr-design-guide.md`](./anpr-design-guide.md).
> For installation angle rules, camera height, modules (MMC/VClass/ADR/speed/red-light), commissioning checklist, and common mistakes, see [`anpr-installation-and-modules.md`](./anpr-installation-and-modules.md).

Only **2 types** of ANPR:

## 1. Stop-and-Go
- Max speed: ~10 km/h — optimized for operational efficiency
- **Applications:** Tolls, ports, parking, gates
- Analytics can run **on-cam** or **on-pc**

## 2. Free-Flow
- Used for: cities, surveillance, security applications
- **Applications:** speeding detection, enforcement, blacklist tracking, vehicle tracking
- Requires higher-end cameras (see below)

### Free-Flow Camera Requirements (e.g. Axis)
- High camera quality
- High pixel quality
- Powerful onboard chip

## Average Speed Detection — Key Fact
- Detection point should be calculated from the **back of the vehicle**, not the front.
- **Why:** front headlights interfere with detection accuracy; rear license plates are typically larger/clearer.
