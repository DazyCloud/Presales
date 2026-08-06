# OEM & SI Partners

Master directory of OEMs by application. Add new companies to this table as they come up. When a company gets its own detailed profile file (like [`07-anpr/vaxtor.md`](../07-anpr/vaxtor.md)), mark it **Yes** below and link the path.

## Master OEM Directory

| Application | Company | Core Features / Best Used When | Detail File? | Path |
|---|---|---|---|---|
| ANPR | Vaxtor | Dashboard: Helix | Yes | [`07-anpr/vaxtor.md`](../07-anpr/vaxtor.md) |
| ANPR | Plate Recognizer | Preferred when high accuracy is required | No | — |
| ANPR | Videonetics | AI-based | No | — |
| ANPR | Vihaan | *(to fill in)* | No | — |
| ANPR | Abmatica | ANPR | No | — |
| ANPR | Vehant | OKEAN/TrafficMon suite — broader AI traffic enforcement (red-light, over-speeding, wrong-way, triple-riding, no-helmet, seatbelt, phone-use, no-parking); claims real-time recognition 200+ km/h | No | — |
| FRS | Oosto | Outdoor — see [`08-frs/frs-overview.md`](../08-frs/frs-overview.md) | No | — |
| FRS | Corsight | Outdoor | No | — |
| FRS | RecFace | Indoor; productized FR workflows — ACS, attendance, workplace identity. Products: IDGate, IDTime, TimeStreet | Yes | [`08-frs/recface.md`](../08-frs/recface.md) |
| FRS | FaceMe | Indoor | No | — |
| FRS | Semi-Index | 3rd FRS category — see [`08-frs/frs-overview.md`](../08-frs/frs-overview.md) | No | — |
| FRS | Herta Security | Crowded-scene FR, centralized surveillance, forensic search — smart city/transport/stadiums/airports | No | — |
| FRS | OOSTO | Real-time POI watchlist alerting + vision analytics on existing CCTV — large venues, campuses, SOC | No | — |
| VA | Davantis | AI video analytics; strong for **perimeter** — see notes below | No | — |
| VA | Citilog | Focused on cities *(features to be understood)* | No | — |
| VA | Icetana | "Minimal action" AI — anomaly/behavior detection *(to fill in further)* | No | — |
| VA | BriefCam | Offline/forensic search, behavior analytics — see [`13-solutions/metro.md`](../13-solutions/metro.md) | No | — |
| VA | BlueCity | Traffic density + vehicle type detection | No | — |
| Lidar | Ouster | See [`11-lidar/lidar-notes.md`](../11-lidar/lidar-notes.md) | No | — |
| Lidar | Hesai | Small size, cheap; e.g. OT128 | No | — |
| Lidar | Opsys | — | No | — |
| PID (fiber-based perimeter) | Gallagher | Fiber-based perimeter / AI fence detection | No | — |
| Radar | Mira Tech | Open areas, range up to 500 m | No | — |
| Access Control | ICT | Access control + intrusion panels | No | — |
| Access Control | Genetec | Access control; Vanilla/Enterprise editions; also preferred for camera-side multicast | Yes | [`04-oem-si-partners/genetec.md`](./genetec.md) |
| Access Control | Suprema | Access control + intrusion panels | No | — |
| VMS | Hanwha Blaze | **Hybrid AI VMS** — "hybrid" = on-premise + cloud, combined with VMS | No | — |

> **VA selection tip:** when evaluating any *new* video analytics company/OEM, always check its **fire and smoke detection capability** as part of the evaluation.

## Proprietary Encoding / Format Names (to fill in as researched)
Some OEMs use their own proprietary encoding/file formats — track them here so integration/compatibility issues can be anticipated.

| Company | Proprietary Encoding/Format Name | Notes |
|---|---|---|
| Genetec | G.264 *(video codec — confirm exact name)* | — |
| *(add more as researched)* | | |

## Davantis — Perimeter Solution Notes
When Davantis is proposed for perimeter security, its preference order/rationale:
1. **Long-range, low-pixel-density detection** — more accurate than alternatives
2. **Tripwire** — an alternative for perimeter, but its challenge is **false alarms**
3. **Lidar** — third solution option for perimeter

*(See also [`09-security-approaches/perimeter-security.md`](../09-security-approaches/perimeter-security.md))*

---
## SI Partners
- *(list SI partners — to fill in)*
