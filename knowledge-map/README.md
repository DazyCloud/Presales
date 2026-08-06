# Knowledge Map

Structured knowledge base for surveillance/security solutioning (ANPR, FRS, VA, VMS, RFP process, networking & hardware fundamentals).

## Folder Structure

```
01-solution-design/     → Deployment types (on-cam/on-pc/on-server/on-edge/on-premises) + decision framework
02-rfp/                 → RFP basics, terms, bidding types (reactive/proactive), portals (GeM) — all in rfp-basics.md
03-hardware/            → Hardware & system requirements, compute specs (incl. memory module types), storage/RAID, networking hardware, requirement gathering & sizing (storage/PoE/bandwidth formulas)
04-oem-si-partners/     → Master OEM directory (by application, with detail-file tracking), model/company selection criteria (NIST/NEC ranking), Davantis perimeter notes, Genetec profile, proprietary encoding formats, SI partners, local companies, camera↔OEM integrations
05-glossary/            → Full forms, basic definitions (incl. resolutions, CapEx/OpEx, SPI, API vs SDK), networking basics (transport/streaming protocols incl. GB/T 28181 & SRT, ONVIF, IGMP/SIP), ratings & standards (IP/IK/PoE/STQC), detection metrics, current tech tracker
06-cameras/             → Camera types, components (lens/sensor/transmitter/form factor), specifications (FPS/bitrate/streams/resolution/shutter/WDR/IR), optics (focal length/FOV/aperture), image sensors
07-anpr/                → ANPR overview, design guide (camera selection, CPU freq, challenges, components, performance parameters, architecture, 4 deployment combos, general design flow), installation & modules (30° rule, height/distance, shutter, modules MMC/VClass/ADR/speed/red-light, commissioning checklist, common mistakes), companies (incl. Plate Recognizer detail), Vaxtor full profile, speed detection
08-frs/                 → FRS use-case framework (cooperative/non-cooperative, real-time/non-real-time, online/offline), pipeline, camera specs, OEM/partner selection, pixel density, RecFace product profile; accuracy metrics, liveness, deployment architecture & security (separate file)
09-security-approaches/ → Perimeter security, access control (components) / anti-tailgating, people counting & crowd management, general video analytics (fall/fight/fire-smoke/accuracy/PSIM) + deployment guide (7-layer pipeline, architecture, metrics, methodology, common mistakes)
10-vms/                 → Video Management System notes
11-lidar/                → Lidar: manufacturers, hardware types, selection criteria, design, spatial intelligence (incl. perception layer), SoC chips + applications (verticals, comparison vs camera/radar/PIR, solution packages, limitations)
12-plc-scada/            → PLC/SCADA/BMS communication protocols
13-solutions/            → Per-vertical solution files: bank branch, ATM, malls, ports, data centres, highway (incl. toll), railway, metro (mandatory security features + BriefCam), airport, factory
```

## Status
Growing structure — most files contain placeholders (`to fill in`) to be completed as more notes come in.
Cross-references between files (e.g. FRS OEM selection ↔ oem-partners.md, multicast OEM ↔ networking-basics.md, camera specs ↔ optics/sensors/components, ANPR design guide ↔ compute-specs.md) are added as `[link](path)` where relevant so logic stays in one place and gets referenced, not duplicated.
