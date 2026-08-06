# Current Technology Tracker

Running list of what's new in the industry, which company makes it, and where it's most popular. Update periodically — this file is meant to stay current, unlike the rest of the glossary.

## CPUs (Server / Workstation / NVR)

| Product Line | Company | Best Suited For | Notes |
|---|---|---|---|
| Core i3 | Intel | Small NVR, light viewing station | Budget, low channel count, no analytics |
| Core i5 | Intel | Small-mid NVR, basic VMS client | Good balance for <16 camera sites, light VA |
| Core i7 / i9 | Intel | Workstation-grade VMS client, mid analytics server | Higher clock speed helps VMS client-side decoding of many streams |
| Xeon Scalable | Intel | Data center / large analytics servers | ECC RAM support, high core count, built for 24×7 server workloads |
| Ryzen 5/7/9 | AMD | Workstations, mid VMS servers | Strong multi-core performance per rupee vs Intel desktop line |
| EPYC | AMD | Large-scale server, dense multi-GPU analytics servers | High core count + PCIe lanes, competes with Xeon in data centers |

## GPUs / AI Accelerators

| Product Line | Company | Best Suited For | Notes |
|---|---|---|---|
| RTX A2000 / A4000 (Ada) | Nvidia | Small-mid analytics server, few dozen VA channels | Workstation-class, lower power draw than data-center cards |
| L4 | Nvidia | Data center inferencing, video analytics at scale | Efficient, purpose-built for AI inference + video decode (NVDEC) |
| T4 (older gen, still common) | Nvidia | Cost-effective inferencing | Widely deployed for FRS/ANPR/VA server workloads |
| A2 / A16 | Nvidia | Dense multi-stream decode + light AI (A16 especially for VDI-style multi-camera decode) | Good where many camera streams need simultaneous decode |
| Jetson Orin Nano / NX / AGX | Nvidia | **Edge/on-cam-adjacent** AI compute (edge boxes, smart cameras, robotics) | Used for On-Edge deployment tier — low power, embeddable |
| Radeon Pro / Instinct | AMD | Alternative GPU compute, less common in VMS/VA ecosystem than Nvidia | Nvidia has stronger software/SDK ecosystem support (CUDA) for VA vendors |

## Camera Chips / SoCs (System-on-Chip)

| Product Line | Company | Best Suited For | Notes |
|---|---|---|---|
| Ambarella (CV/S-series) | Ambarella (USA) | Mid-high-end IP cameras with on-camera AI | Common in premium camera brands for on-cam analytics |
| Hi3516/Hi3519 series | HiSilicon (Huawei) | Mass-market to mid-range IP cameras | Extremely common in Hikvision/Dahua-ecosystem and OEM cameras |
| SigmaStar (formerly part of MStar) | SigmaStar | Budget-mid IP cameras | Common alternative to HiSilicon after export restrictions |
| RV1109/RV1126 series | Rockchip | AI-capable edge cameras, NVRs | Popular for AI-enabled budget/mid cameras |
| Snapdragon (embedded) | Qualcomm | Higher-end smart cameras, some body-worn/edge AI devices | Less common in mainstream CCTV, more in specialized/edge AI devices |
| Novatek | Novatek (Taiwan) | Budget cameras, ISP (image signal processor) duties | Often paired with another chip for AI |

## Motherboards / Server Platforms

| Company | Best Suited For | Notes |
|---|---|---|
| Supermicro | Rack servers, GPU-dense analytics servers | Industry standard for purpose-built server builds |
| Asus (Server/WS series) | Workstation-class servers, mid analytics builds | Good middle ground between desktop and full enterprise server boards |
| Gigabyte (Server series) | Rack/GPU servers | Competes directly with Supermicro for GPU server chassis |
| MSI (Server/Pro series) | Workstation builds | Less common than Supermicro/Gigabyte for pure server deployments |
| Dell (PowerEdge), HPE (ProLiant), Lenovo (ThinkSystem) | Enterprise turnkey servers | Full server (board + chassis + support/warranty) — preferred for large enterprise/government RFPs needing OEM support/AMC |

## Cabling

| Type | Company / Standard | Best Suited For | Notes |
|---|---|---|---|
| Cat5e / Cat6 / Cat6a | Standard (multiple vendors — D-Link, Legrand, AMP/CommScope) | Standard camera runs up to 100m | Cat6a supports 10Gbps over longer runs than Cat6 |
| Single-mode fiber | CommScope, Corning | Long-haul links (>100m), inter-building | Needs media converters/SFPs at each end |
| Multi-mode fiber | CommScope, Corning | Shorter high-speed campus links | Cheaper transceivers than single-mode |
| DAC (Direct Attach Cable) | Various (switch-vendor specific, e.g. Cisco, MikroTik) | Short switch-to-switch/server links | Cheaper and lower-latency than fiber+SFP for short distances |

## Monitors / Video Walls

| Company | Best Suited For | Notes |
|---|---|---|
| Dell, LG, Samsung | Standard operator workstation monitors | 24-32" for VMS operator desks |
| ViewSonic, BenQ | Budget-mid control room monitors | Common in mid-size control rooms |
| Barco, Planar, Christie | Large-format video walls, command/control centers | Purpose-built for 24×7 video-wall operation, higher cost, better brightness/uniformity for tiled displays |

## Cameras (recap — full detail in [`04-oem-si-partners/oem-partners.md`](../04-oem-si-partners/oem-partners.md))

| Company | Best Suited For | Notes |
|---|---|---|
| Hikvision, Dahua | Mass-market to enterprise, wide product range | Largest global market share; strong on-cam AI feature set at competitive price |
| Axis Communications | Premium/enterprise, mission-critical sites | Higher cost, strong reputation for reliability, open platform (ACAP) |
| Bosch | Enterprise, industrial/critical infrastructure | Strong build quality, integrates well with enterprise VMS |
| Hanwha (Wisenet) | Enterprise, banking/retail | Strong WDR/low-light lineup |
| CP Plus, Prama, Matrix, Sparsh | Indian-made / "Make in India" — STQC:ER:01 compliant | Preferred for government/regulated tenders requiring domestic origin |

*(Update periodically — this file is meant to stay current, unlike the rest of the glossary. Verify latest generation/model numbers before quoting in an RFP, as these refresh every 1-2 years.)*
