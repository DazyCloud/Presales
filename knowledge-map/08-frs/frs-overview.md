# FRS (Face Recognition System) — Overview

## 1. First: Define the Use Case
Before anything else, classify the use case. Two independent axes matter:

### A) Cooperative vs Non-Cooperative
| | Cooperative | Non-Cooperative |
|---|---|---|
| Subject behavior | Subject pauses/faces camera on purpose (e.g. door, kiosk) | Subject is moving, not posing (e.g. crowd, street) |
| Compute need | **Less compute** — smaller search, controlled capture | **More compute** — larger search space, more variation |
| Most important factor | Enrollment quality, threshold | **Camera position** is critical |

### B) Real-Time vs Non-Real-Time
| Type | Use Case |
|---|---|
| **Real-time** | ACS (Access Control System) — instant decision needed |
| **Non-real-time** | Investigation — forensic/search after the fact, latency not critical |

### C) Online vs Offline
| Type | Sub-Category | Examples |
|---|---|---|
| **Online** | Operational | Authorized/unauthorized checking — office, hotel |
| **Online** | Surveillance | City-level blacklist or missing-person alerting |
| **Offline** | Surveillance | Video footage review, detection logs (forensic search — not real-time) |

## 2. Cooperative vs Non-Cooperative — Camera Spec Table
| Parameter | Cooperative (e.g. door, kiosk, ACS) | Non-Cooperative (e.g. surveillance, crowd) |
|---|---|---|
| Resolution | 2 MP minimum (close-range) | 4 MP+ (higher — wider/variable capture) |
| FPS | 25–30 fps | 25–30 fps (same, but need faster shutter for motion) |
| Focal length | Fixed lens OK if distance is controlled | Varifocal / motorized zoom — distance varies |
| Sensor size | Standard | Larger sensor preferred (low light, wider scenes) |
| WDR / IR | Strong WDR for mixed light; IR if low light | Strong WDR + IR — less control over lighting |
| Distance of capture | Known, fixed (e.g. 0.5–2 m at a door) | Variable — must be designed via capture zone |
| Face width | ≥80 px minimum, 100+ px preferred | Same targets, but harder to guarantee |
| Mounting height | ~1.4–1.8 m (eye level) | Avoid steep top-down angles; use dedicated capture cameras at choke points instead of only overview cameras |

## 3. Why FRS is More Challenging Than ANPR
Faces vary more than plates: varying **pose**, **lighting**, and **appearance**.

## 4. The FRS Pipeline (4 Core Steps)
1. **Face Detection** — locate face in frame. Models: RetinaFace, MTCNN, YOLOFace.
   - MTCNN = cascade of 3 neural nets: P-Net → R-Net → O-Net.
2. **Face Alignment** — locate landmarks (eyes/nose/mouth), normalize position.
3. **Feature Extraction** — convert face into a mathematical vector (**embedding**).
   - Stored template size: **1–5 KB** per face.
4. **Face Matching** — compare embedding to database via similarity threshold.

### Matching Thresholds (Face Width in Pixels)
| Face Width | Result |
|---|---|
| 100–200 px | Good recognition |
| Up to 40 px | Detection only, not reliable recognition |
| ≥80 px | Minimum for dependable recognition |
| ≥120–150 px | High-confidence threshold |

> License plate width for high-confidence ANPR is 120–200 px, for reference.

## 5. Use-Case Distance & Camera Requirements
| Use Case | Distance | Camera |
|---|---|---|
| Door access | 0.5–2 m | 2–8 MP |
| Office entrance | 2–5 m | 2–4 MP |
| Public surveillance | 10–30 m | 4–8K cameras |

> **Pixel density** here = camera resolution ÷ scene width (same width, more resolution = more pixels on subject).

## 6. FRS Application Use Cases
- Search for any specific person
- Find a missing person / suspect
- Watchlist monitoring
- Track a suspect after an incident (investigation support)
- Search an incident using **GenAI** — by person characteristics
- Video summarization
- Crowd density / queue monitoring, overcrowding detection
- General AI-based detection

## 7. Camera Types by Use Case
| Camera Type | FR Suitability | Best Application |
|---|---|---|
| Dedicated FR terminal | Excellent | Door access, attendance, turnstiles |
| Fixed dome | Good (controlled scenes) | Office entries, reception, short corridors |
| Varifocal bullet | Excellent | Outdoor gates, perimeter, variable distances |
| PTZ | Situational | Tracking, not ideal as primary FR camera |
| Fisheye / panoramic | Poor as primary FR source | Overview only — pair with a dedicated capture camera |

## 8. Mounting Height Guide
| Location | Height |
|---|---|
| Access terminal / door camera | 1.4–1.8 m (near eye level) |
| Face-capture camera, controlled lane | Keep angle shallow, distance stable |
| Overhead surveillance | Only if face pixel density still workable — validate on-site |

## 9. OEM Selection — Indoor vs Outdoor vs Semi-Index
3 categories for selecting an FRS OEM:

| Environment | Preferred OEM | Notes |
|---|---|---|
| **Outdoor** | Oosto, Corsight | Better for variable lighting/angle |
| **Indoor** | RecFace, FaceMe | Preferred for controlled indoor lighting |
| **3rd type** | Semi-Index | *(to fill in — when/why to use)* |

> See also the master OEM directory: [`04-oem-si-partners/oem-partners.md`](../04-oem-si-partners/oem-partners.md).

### Platform Partner Positioning (by scenario)
| Partner | Core Strength | Best-Fit Scenarios |
|---|---|---|
| **Herta Security** | Crowded-scene FR, centralized surveillance, forensic search | Smart city, transport hubs, stadiums, airports, command centers |
| **OOSTO** | Real-time POI (person-of-interest) watchlist alerting + vision analytics on existing CCTV | Large venues, campuses, retail security, enterprise SOC, critical infrastructure |
| **RecFaces** | Productized FR workflows — ACS, attendance, workplace identity | Corporate access, attendance, visitor flows, smart offices |

> **Rule of thumb:** match platform to use case. Herta = surveillance. OOSTO = real-time POI alerting. RecFaces = workplace/access.

## 10. Pixel Density Requirements (by detection type)
| Detection Type | Pixel Density | FPS |
|---|---|---|
| Face detection | 90–120 ppf (pixels per face) | — |
| Person detection | 10–20 ppf | 10 fps |
| Vehicle detection | 3–10 ppf | — |
| License plate (ANPR) | 100–300 ppf | 30+ fps |

## Licensing Notes
- **Oosto** — no charge *(for what specifically — to confirm/fill in)*

## Hardware Companies
- *(list companies that build FRS-capable hardware — to fill in)*

---
> For accuracy metrics, liveness/anti-spoofing, deployment architecture, and security hardening, see [`frs-accuracy-and-deployment.md`](./frs-accuracy-and-deployment.md).
