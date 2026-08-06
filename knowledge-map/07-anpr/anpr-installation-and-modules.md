# ANPR — Installation Rules, Modules & Commissioning

*(Sourced from ANPR Technology & System Training Guide — adds detail not already covered in `anpr-design-guide.md`.)*

## ANPR's 5 Core Jobs
1. **Capture** — get a usable vehicle image/frame (sharpness + contrast)
2. **Detect** — locate the plate region, separate from clutter/stickers/reflections
3. **Read** — OCR + AI to convert plate image to text
4. **Enrich** — add time, lane, camera ID, direction, speed, vehicle class, evidence snapshot
5. **Act** — match against rules/watchlists/tolling/access lists, trigger downstream action

## Trigger Models — How ANPR Systems Operate
| Model | How It Works | Best For |
|---|---|---|
| **Continuous Video Analysis** | Engine inspects every frame, no external trigger | Free-flow environments |
| **Triggered Capture** | Loop detector, radar, barrier controller, or app rule triggers the read at a precise point | Controlled environments — improves accuracy, reduces load |

## Installation Angle Rules (Critical)
- **30-Degree Rule:** keep BOTH vertical angle and horizontal angle below 30° — angle between lens and farther lane border, and lens-to-ground angle, must both stay under 30°
- **Plate inclination angle:** must stay below **5°**
- Beyond 30°, characters appear compressed/distorted, OCR confidence drops sharply — this holds even with high-quality cameras/software

## Camera Height & Recognition Distance
- Height itself is NOT the main metric — what matters is: **plate view angle, recognition distance, headlight influence, and whether the read point is front/rear/lateral/overhead**
- Reference heights (vary by source/geometry):
  - Lateral installation: ~1.5 m minimum
  - Transversal/overhead: ~2.5 m minimum
  - Some designs: ~0.9 m above ground for best viewing angle
- **Recognition distance:** typically 1.5 m – 15 m (longer with telezoom)
- **Design rule:** design backward from the angle constraint to the height — not the other way around

## Shutter Speed & Motion Blur
- Generic CCTV shutter settings are almost never appropriate for ANPR
- May need shutter speed as fast as **1/20,000 sec** in difficult (high-speed) scenarios
- Trade-off: faster shutter → less blur, but needs more light (wider aperture/stronger illumination/better sensor)

## Minimum Character Height (Design Targets, Not Minimums to Barely Meet)
| Script | Minimum Character Height |
|---|---|
| Latin characters | 16 px |
| Arabic characters | 20 px |

> **Megapixel myth:** total camera megapixels doesn't guarantee good ANPR — what matters is **plate pixel density at the recognition point**. A 4K camera with a wide lens can deliver fewer plate pixels than a 2MP camera with the right varifocal lens.

## Lens Type Comparison
| Lens Type | Best For | Note |
|---|---|---|
| **Fixed** | Only when geometry is tightly known and won't change | Least flexible — use with caution |
| **Varifocal** | Usually the best ANPR choice | Lets engineer tune FOV during commissioning |
| **Motorised Zoom** | Highway corridors, remote fine-tuning, hard-to-access sites | Iterative adjustment without physical camera access |

## Sun & Headlight Management
**What to avoid:** camera facing directly into sun or headlights; overexposed plates from bad camera/illuminator balance; strong backlight without proper shutter/WDR correction.
**Best practice:** sunlight from the side (not behind camera/vehicle); test day AND night during commissioning; use WDR + ANPR-specific shutter tuning.

## Lane Coverage
- **One camera per lane** is the safest principle for enforcement/high-accuracy environments
- Multi-lane coverage is **model-specific** — never assume; wider lens for multi-lane = lower plate pixel density trade-off

## Camera Selection: Purpose-Built vs Premium IP + Software
| | Purpose-Built ANPR Camera | Premium IP Camera + ANPR Software |
|---|---|---|
| Best for | High-speed highways, enforcement, strong integrated IR/WDR, tight lane control, simplified commissioning presets | Cities with existing CCTV, campuses, parking, moderate speed, multiple analytics beyond OCR needed |
| Trade-off | Enforcement-grade evidence quality | Can scale city-wide and reduce cost by reusing existing IP camera ecosystem |

## Modules Beyond Base OCR
| Module | What It Does | Add When |
|---|---|---|
| **License Plate OCR** | Base module — reads plate, publishes string + evidence + metadata | Always (foundation) |
| **Hotlist/Watchlist Matching** | AI matching for stolen/wanted/VIP vehicles, multi-location alerts | Policing, border, enterprise, smart-city |
| **MMC (Make/Model/Colour)** | Vehicle attribute recognition — e.g. 200+ makes, 4,500+ models, real-time on PC or embedded | Richer investigation, false-plate/fraud detection, KYC, access-control validation |
| **VClass (Vehicle Classification)** | Classifies motorcycle/car/van/bus/truck | Traffic counting, toll class validation, congestion analysis |
| **Speed Measurement** | Single-camera instantaneous speed estimate, best on front plates | Smart-city traffic monitoring, industrial site speed control |
| **Red-Light Enforcement** | Detects red-light status via imaging (no physical signal connection); sequenced violation evidence; supports up to 4 ALPR cameras per signal | Multi-lane signal enforcement |
| **ADR (Dangerous Goods Recognition)** | Reads hazmat plates incl. HIN + 4-digit UN Kemler codes | Oil/gas sites, ports, tunnels, logistics hubs, border corridors — anywhere hazmat trucks may enter |
| **TrafficMon-style modules** | Wrong-way driving, helmet/triple-riding/seatbelt, driver-on-phone, no-parking violation detection | Broader ITMS enforcement stack (common in Indian deployments), not standalone OCR |

> **AI features that improve the OCR engine:** AI-assisted plate detection (handles clutter/reflections/weather), orientation handling (zero-calibration vehicle orientation via MMC), vehicle attribute fusion (plate + "white SUV" > plate alone for forensic search), fraud detection support (MMC flags plate/vehicle mismatch), real-time event detection/validation.

## Journey-Time & Average-Speed Analytics
- Vehicle read at Camera A, then Camera B → system calculates elapsed time ÷ known distance = **average speed** (more reliable than instantaneous speed for enforcement)
- Feeds congestion management, variable message signs, route planning, transport dashboards
- Typically visualized in back-office platforms (e.g. Helix) as corridor-level analytics, heat maps, time-series reports

## Sector-Specific Installation Patterns
| Site Type | Key Pattern |
|---|---|
| **Gate/Barrier Access** | Front-plate capture, controlled stop line, varifocal lens, strong whitelist/hotlist logic, tested ACS/barrier integration |
| **Highway/Expressway** | High shutter speed mandatory, one lane per camera, strong IR, speed/direction/evidence modules included |
| **City Intersection** | ANPR + ITMS integration, add-on violation modules, multi-camera by lane count, city dashboard integration |
| **Logistics Yard / Port Gate** | Plate OCR + MMC + VClass + ADR, container/truck/trailer handling, weighbridge/gate control/ERP/yard mgmt integration |

## Common Engineering Mistakes (Checklist)
1. Wide lens capturing too much scene, too little plate detail
2. Angle violations — mounting too high/off-axis (>30°)
3. Ignoring night headlight behavior during design
4. Assuming multi-lane coverage without model-specific proof
5. Using generic CCTV shutter settings instead of ANPR-specific tuning
6. Designing by total megapixels instead of plate pixel density at recognition point
7. Ignoring back-office/integration/evidence-retention design
8. Not validating with actual local plate styles/fonts/materials

## Commissioning Checklist
**Physical Installation**
- Camera angle below 30° (vertical + horizontal)
- Recognition point selected, lens focused there
- No overexposure/blur in plate images
- Day AND night headlight/sun tests completed
- Lane coverage verified physically + in software
- Plate inclination angle below 5° confirmed

**Performance & Integration**
- Read confidence / missed-read rate tested on actual traffic
- Watchlist/whitelist alerts validated end-to-end
- Evidence images include readable plate + contextual scene
- Integration to ACS/VMS/ITMS/back-office confirmed
- Retention, search, reporting tested
- Night performance validated under actual site conditions

## The 5 Questions Every ANPR Engineer Must Answer
1. What is the customer trying to achieve?
2. What plate view quality is required (recognition rate, speed range, day/night, evidence quality)?
3. What camera/lens/angle/lighting combination guarantees that quality? *(work backward from quality requirement to physical design — never the reverse)*
4. What analytics/modules are needed beyond OCR (MMC/VClass/ADR/speed/red-light)?
5. What back-office, network, and integration design makes the result operationally useful?

## System Design Layers (Top to Bottom Dependency)
```
Management Layer     → back-office, hotlists, search, reporting, evidence export
Integration Layer    → ACS, VMS, ITMS, ERP, police databases, tolling
Analytics Layer      → MMC, VClass, ADR, speed, red-light, wrong-way
Processing Layer     → edge OCR / server OCR, confidence scoring, AI detection
Physical Layer       → camera, lens, illumination, mounting, angle, height
```
> A weak physical layer cannot be compensated by a strong OCR engine. A strong OCR engine without a strong back-office delivers reads that can't be acted on.

## Two Reference Deployment Approaches
| | Vaxtor-style (Platform Approach) | Vehant OKEAN-style (Enforcement Engine) |
|---|---|---|
| Emphasis | Expanded AI features beyond OCR, multi-vendor integrations (MMC, ADR, red-light, speed, smart-city/Helix) | AI-driven traffic violation detection suite (TrafficMon: red-light, over-speeding, wrong-way, triple-riding, no-helmet, seatbelt, phone-use, no-parking), centralized multi-location monitoring |
| Positioning | Vehicle intelligence platform | Broader AI enforcement platform, optimized for ITMS deployments (e.g. India) |

