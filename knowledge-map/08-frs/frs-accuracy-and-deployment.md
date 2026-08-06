# FRS — Accuracy, Liveness, Architecture & Security

## Key Accuracy Metrics
| Metric | Meaning | Why It Matters |
|---|---|---|
| **FAR / FMR** | False Acceptance / False Match Rate | How often an impostor is wrongly accepted |
| **FRR / FNMR** | False Rejection / False Non-Match Rate | How often a genuine user is wrongly rejected |
| **EER** | Equal Error Rate | Quick benchmark — lower is better |
| **Detection Rate** | % of visible faces actually detected | If detection fails, recognition can't happen |
| **Quality Score** | Suitability of captured face for matching | Rejects poor captures before matching |
| **Top-N Rank** | Whether correct identity appears in top candidates | Useful for forensic search |
| **Latency** | Time from capture to decision | Critical for access control / real-time alerting |

> **Threshold tuning is a trade-off:** higher threshold = fewer false accepts but more false rejects. Access control needs a stricter threshold than soft-alert surveillance.

## 1:1 Verification vs 1:N Identification
| Mode | Question | Search Space | Use Case |
|---|---|---|---|
| **1:1 Verification** | Is this the claimed person? | 1 live face vs 1 enrolled template | Door access, attendance, workstation login |
| **1:N Identification** | Who is this person? | 1 live face vs entire gallery/watchlist | Surveillance, watchlist alerting, forensic search |

> Verification is generally more accurate (narrower scope). Identification is more compute-heavy and more sensitive to threshold, database size, and image quality.

## Liveness Detection / Anti-Spoofing (4 Types)
| Type | How It Works | Best For |
|---|---|---|
| **Active** | User must blink/turn/smile on prompt | Controlled access points; needs user cooperation |
| **Passive** | Analyzes texture/reflectance/depth/motion, no user action | Frictionless workflows |
| **IR / NIR-assisted** | Infrared response tells real skin from a print/replay | Low-light; basic spoof resistance |
| **3D Sensing** | Structured light / stereo / depth sensors verify geometry | Strongest — against masks + advanced spoofing |

## Deployment Architecture (3 Types)
| Architecture | Description | Best Fit |
|---|---|---|
| **Edge AI** | Detection/recognition on camera or nearby edge device | Door access, attendance, local watchlist, weak WAN sites |
| **Server-Based** | Cameras = video source only; matching runs on GPU servers | Large galleries, cross-camera forensic search, centralized ops |
| **Hybrid** | Edge response + centralized watchlist/audit/management | Most enterprise deployments — balances speed + central visibility |

## CPU vs GPU Roles in the FRS Pipeline
| Processor | Handles |
|---|---|
| **CPU** | Sequential logic, face detection (initial), I/O, database queries, system orchestration |
| **GPU** | Feature extraction (embeddings), matching/scoring, deep-learning inference — the parallel-heavy work |

## Storage Design — 3 Layers
| Layer | Purpose | Retention |
|---|---|---|
| Full video | Investigation/audit | Per site policy |
| Face-capture events/thumbnails | Operator review | Shorter, faster access |
| Biometric templates + watchlist metadata | The recognition DB itself | Needs strong access control + encryption |

## ONVIF Profile M (FRS-Relevant)
- Supports analytics config, metadata query/streaming, and event handling for analytics like face recognition.
- Supports event transport via metadata streams, ONVIF event service, and MQTT (where supported).
- **Important:** ONVIF support alone ≠ full FRS interoperability — always validate the actual metadata/event path during integration.

## Security Hardening — Attack Surfaces to Address
- Camera/stream — feed hijacking, video injection
- Credentials & access — weak passwords, insider misuse
- Database & enrollment — unauthorized enrollment/watchlist edits, weak audit logs
- API & integration — abuse between FR engine, VMS, ACS, identity systems
- Presentation attacks — photo, replay video, 3D mask

## Failover Behavior by Use Case
| Use Case | Failover Approach |
|---|---|
| Access control | Fail-secure (locked) vs fail-safe (unlocked) vs fallback to card/PIN |
| Attendance | Offline buffering at terminal, sync when connectivity restores |
| Surveillance | Keep recording, delay analytics processing |
| Distributed branches | Local edge decision-making, central sync on restoration |

## Enrollment — Good Practice
- Sharp, front-facing images, even lighting
- Avoid sunglasses, strong shadows, motion blur, heavy compression
- No duplicate records for the same person
- Use recent images (hairstyle/beard/age drift matters)
- Apply a minimum quality rule before adding to database

## Site Survey Checklist (before installation)
- Capture-zone width and subject distance
- Lighting level at face height, day + night
- Windows, reflective surfaces, backlight sources
- Environment: heat, dust, rain, sunlight
- Tamper/vandal risk, enclosure needs
- **User behavior: cooperative or non-cooperative**
- Throughput / speed of movement
- Network, PoE, switch, rack availability
- Edge vs central processing decision
