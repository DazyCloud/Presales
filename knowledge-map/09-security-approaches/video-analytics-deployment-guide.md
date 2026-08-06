# Video Analytics — Pipeline, Architecture & Deployment Guide

*(Companion to `video-analytics-general.md` — adds pipeline, architecture, metrics, and deployment methodology.)*

## The 7-Layer Analytics Pipeline
Analogy: camera = the eye, AI model = the brain, VMS + operator workflow = the nervous system.

1. **Image Acquisition** — fixed, PTZ, body-worn, drone, IR, or thermal cameras; input quality caps all downstream performance
2. **Video Transport** — RTSP, ONVIF, or VMS-managed protocols over IP; bandwidth/reliability affect latency
3. **Frame Preprocessing** — stabilization, denoising, resizing, perspective correction, exposure normalization
4. **AI Inference / Rule Execution** — core engine detects objects/events/abnormalities via deep learning or rule logic
5. **Multi-Stage Verification** — confidence scoring + false-alarm suppression before an alert is raised
6. **Event Generation** — packages verified events with metadata: time, camera ID, location, object class, snapshot, clip
7. **Alert Delivery** — reaches operators via VMS, web, mobile, or command-control; triggers investigation/escalation

## Rule-Based vs AI Behavior-Based vs Hybrid
| Approach | How It Works | Best For | Weakness |
|---|---|---|---|
| **Rule-Based** | Engineer defines conditions (line cross, zone intrusion, object left, direction violation); alert fires only when triggered | Tightly controlled scenes: sterile corridors, fence lines, toll booths, gates, lane monitoring | Gets noisy with shadows, weather, clutter, lighting shifts, camera shake, reflections |
| **AI Behavior-Based** | Learns what's "normal" per camera via ML/DL, flags deviations; self-learning starts within ~24 hrs, improves over time | Large/dynamic scenes where not every threat can be pre-defined | Needs a learning period before reliable |
| **Hybrid (most production systems)** | Rules handle compliance/precise triggers (fence line, sterile zone, lane violations, ACS triggers); AI adds classification/anomaly scoring/false-alarm filtering on top | Real-world deployments — best of both | More complex to design/tune |

> Example: a decision layer (e.g. "Charon"-style) verifies suspicious content before forwarding alerts — cuts nuisance alarms dramatically.

## Feature Taxonomy (Learn by Family, Not Vendor List)
| Family | Includes |
|---|---|
| **Perimeter & Intrusion** | Line crossing (tripwire), zone intrusion, fence approach/sterile zone, wrong-way/restricted-hours |
| **Safety & Hazard** | Smoke/fire, fall/slip, aggressive behavior/fight, PPE/safety-gear audit |
| **Crowd & People Flow** | People counting (bi-directional), queue monitoring, crowd density/congestion, loitering, occupancy/dwell patterns |
| **Identity, Access & Retail** | Face watchlists, face auto-enrollment, attendance workflows, visitor management, shoplifting indicators, unauthorized-area access, asset protection, after-hours occupancy |
| **Vehicle & Traffic** | Detection/classification, speed workflows, lane violation/wrong-way, ANPR/LPR integration, stopped-vehicle detection, traffic flow/congestion, parking occupancy, boom-barrier access |
| **Threat Detection** | Weapon detection, aggressive behavior, smoke/fire, perimeter intrusion (verified), face watchlists, vehicle ID linked to watchlists |

## Architecture: Edge / Server / Hybrid
| Architecture | How It Works | Benefits | Considerations |
|---|---|---|---|
| **Edge** | Inference on camera/edge appliance; only events+metadata travel upstream | Lower bandwidth, faster local decisions, scales to distributed sites, resilient to WAN loss | Limited compute constrains model complexity; firmware/appliance management overhead |
| **Server-Based** | Raw/compressed streams sent to centralized GPU/CPU servers | Simpler central management, stronger compute for heavy models | Higher network dependency, needs careful stream-count/bitrate sizing |
| **Hybrid (most common in practice)** | Edge does first-pass (motion, line-crossing, basic detection); server does deep classification/anomaly scoring/watchlist matching/forensic search; VMS does correlation/display/escalation | Balances both models' strengths | More design complexity across layers |

## Camera & Scene Requirements (Analytics Quality Ceiling)
- **Resolution & pixel density** — sufficient pixels on target for the object size/detection distance needed
- **Stable mounting** — camera shake degrades detection accuracy significantly
- **Adequate illumination** — correct lighting for scene/time of day, incl. WDR for entrance transitions
- **Thermal/IR support** — required for night/low-visibility (borders, oil & gas)
- Common failure mode: a "weak" analytic often isn't weak software — it's too few pixels on target, headlight/rain glare, or camera shake from wind

## Network & Compute Sizing Checklist
- Camera count and bitrate per stream
- Number of concurrent analytic streams
- GPU vs CPU processing requirements
- Event metadata and snapshot storage
- WAN bandwidth for remote sites
- VMS integration overhead
- Retention periods — recordings vs events (separate!)
> Note: mainstream may be used for recording while substream is used for some analytic tasks depending on model needs.

## Performance Metrics Every Engineer Must Track
| Metric | What It Measures | Why It Matters |
|---|---|---|
| **Detection Rate / Recall** | True events actually detected | High recall = fewer missed incidents |
| **Precision** | How many alerts are actually relevant | Low precision → operator alert fatigue → system gets ignored |
| **False Alarm Rate** | Nuisance-event frequency | #1 driver of operator distrust in analytics |
| **Time-to-Alert** | Speed from event to operator notification | Critical for live threats (weapon, breach) |
| **Investigation Time Saved** | Efficiency gain from metadata-driven search vs manual review | Key for forensic/anomaly systems |

> Reference figures from vendor claims (treat as starting points, always validate on-site): 99.95% false-alarm filtering (specialist threat platforms), 99% video-overload reduction (self-learning anomaly platforms), learning starts within 24 hrs.

## Deployment Methodology (10 Stages)
1. **Define the operational problem** — not just a feature name (e.g. "detect unauthorized persons in server room 10pm–6am", not "we need intrusion detection")
2. **Survey site conditions** — camera positions, lighting, scene dynamics, weather, network, power
3. **Select analytics type** — rule-based, behavior-based, or hybrid, based on use case + false-alarm tolerance
4. **Validate pixel density** — confirm target pixel density/FOV with sample footage before committing to camera positions/lenses
5. **Size infrastructure** — compute, storage, network for the FULL deployment, not just phase 1
6. **Integrate with VMS & workflows** — before acceptance testing begins
7. **Run acceptance tests** — real scenarios, not just vendor demos; simulate actual threat + nuisance conditions
8. **Tune zones & thresholds** — based on test results and operator feedback
9. **Train operators** — document escalation rules
10. **Review & optimize** — after go-live, review false alarms/missed events, then retune

## Common Deployment Mistakes
1. Choosing analytics before defining the use case
2. Using overview/wide-angle cameras for identification tasks (insufficient pixel density for face/plate/behavior)
3. Ignoring nighttime conditions during POC (daylight-only testing hides real performance gaps)
4. Trusting vendor accuracy claims without on-site validation
5. Sending every stream to a central server without bandwidth planning
6. Designing detection without designing the operator workflow around it
7. Expecting self-learning anomaly systems to perform well on day one (before the learning period completes)
8. Not planning for continuous tuning as scenes/seasons/operations change (analytics is not "set and forget")

## Integration Requirements
- **VMS** — almost always mandatory: event push, bookmarks, operator display
- **Access Control** — required for identity-linked/access-triggered use cases
- **PSIM/Command Centers** — required for multi-system/city-scale deployments
- **Traffic/GIS** — required for highway/city/transport hub deployments

## The 5 Questions Every VA Solution Engineer Must Answer
1. What exact operational problem is being solved? (specific, measurable outcome — who needs to know what, when, and what action follows)
2. Is the requirement rule-based, behavior-based, or hybrid?
3. Are the existing cameras and scene conditions actually suitable?
4. What modules are needed now vs later? (plan for full scope to avoid re-architecture)
5. Where will analytics run — camera, edge box, or server?
6. *(Also: how will alerts reach operators and who acts on them? What false-alarm level is acceptable? Which integrations — VMS/ACS/PSIM/traffic — are mandatory?)*

## Explaining Value to Customers (Speak Operational, Not AI)
| Vertical | What They Value Most |
|---|---|
| Smart City | Citywide situational awareness, faster incident discovery, reduced operator overload |
| Highway | Quicker incident response, ANPR enforcement integration |
| Data Center | Low false alarms, strict sterile/restricted-zone monitoring |
| Retail | Loss-prevention ROI, queue management efficiency |

General messaging: fewer missed incidents, faster response, better use of manpower, stronger evidence, safer sites.
