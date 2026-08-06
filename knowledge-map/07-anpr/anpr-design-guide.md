# ANPR — Design & Selection Guide

## Camera Selection

### Lane-Based Resolution
| Lanes Covered | Suggested Resolution |
|---|---|
| 1 lane | 5 MP (single lens — for reading the plate) |
| 2 lanes | 5 MP suggested (2 lenses → 2 MP per frame is an alternative config) |

> **2 lenses setup:** 2 MP per frame (wider framing).
> **1 lens setup:** 5 MP (dedicated plate resolution).

### Internal IR — Brand vs Non-Brand
- **Brand (OEM) IR modules:** 2 MP is generally acceptable — what matters is **effective pixel count**, not just stated MP.
- **Non-brand:** *(quality/considerations to fill in)*

### Other Selection Factors
- Resolution
- Brand vs non-brand
- **Focal length:** e.g. 10x zoom for ~200 m range — used for highway
- **Zoom:** 2x (front-facing), 4x (side-facing)

### Front vs Back View Requirements
| View | Free-Flow (Front View) | Back View |
|---|---|---|
| Key specs | IR, WDR | WDR, Aperture, Shutter Speed, Varifocal Lens, SD Card Class |

### Camera Type by Deployment
| Deployment | Camera Type |
|---|---|
| Gate | Bullet camera + inbuilt IR |
| Stop-and-Go | Bullet camera + inbuilt IR *(note: inbuilt IR is not suitable for Free-Flow)* |

## CPU Base Frequency (by ANPR type)
| ANPR Type | Min. Base Frequency |
|---|---|
| Stop-and-Go | 2.5 GHz |
| Free-Flow | 3.0 GHz |

*(see also [`03-hardware/compute-specs.md`](../03-hardware/compute-specs.md))*

## ANPR System Components
1. Camera subsystem
2. Lens
3. Illumination
4. OCR
5. Edge / server compute
6. Back office

## Plate Localization Techniques
(How the system finds the plate within the frame, after a vehicle is detected)
1. Edge detection
2. Contour analysis
3. Deep learning (DL) models

## Common Challenges
- Motion blur
- Overexposure
- Plate pixel density (too low)
- IR interference/insufficiency
- Shutter setting (wrong speed for vehicle speed)
- Local plate format variation

## Ways to Enhance an ANPR System
- AI assistance
- Orientation handling (angled plates)
- Vehicle attribute fusion (OCR + MMC [Make/Model/Colour] + VClass [vehicle classification])
- Fraud detection support

## Performance Judging Parameters
When evaluating an ANPR system/OEM, check it against:
1. Works in all conditions (lighting variation)
2. Handles any plate style, at any speed
3. FD (Fault/Failure Detection?) management *(confirm exact meaning)*
4. Day/night stability
5. Lane coverage
6. Direction of plate read (front, rear, both)
7. Architecture (edge vs server)
8. Integration scope (VMS, ACS, ITMS, back office)

## Deployment/Design Considerations
- Headlight / illumination management
- Camera mounting height
- Plate view angle
- Recognition distance
- Headlight influence on the shot
- Plate location (front vs rear)

## Architecture Choice: Edge vs Server
| Architecture | When to Use |
|---|---|
| **Edge** | Reduces bandwidth and server load |
| **Server** | Needed when multiple streams must be aggregated, managed, and searched together |

## Questions to Ask Before Proposing an ANPR Solution
- Purpose
- Quality requirement
- Camera / lens / mounting angle
- Lighting conditions
- Analytics needed
- Back-office requirement (if more analytics is needed, back office becomes necessary)

## 4 Possible ANPR Deployment Combinations
| # | Combination | When Used |
|---|---|---|
| 1 | **On-Cam + VMS** (VMS acts as the container) | Basic deployments |
| 2 | **On-Cam + Helix** (Helix acts as the container) | Multiple cameras, need detailed reporting, watchlist — e.g. manufacturing unit |
| 3 | **On-PC + Helix** | Cities (city-scale deployments) |
| 4 | **On-PC + VMS** | Rare combination |

## General Solution Design Flow
Follow this sequence when designing any ANPR (or similar camera-based) solution:

```
Use case
  → Edge or Server (architecture)
    → On-Cam / On-PC module
      → Detection distance
        → Identification vs Detection (which is actually needed)
          → Camera type & resolution
            → IK / IP rating (important for gate deployments)
              → Lens (mm & type)
                → Mounting height
                  → Viewing angle
                    → Lighting condition
                      → Integration requirement (VMS/ACS/ITMS/back office)
                        → Storage, compute & network sizing
```
> This flow generalizes beyond ANPR — it's a useful checklist order for most camera-based solution designs.
