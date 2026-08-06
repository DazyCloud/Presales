# Image Sensors — Reference

## Sensor Types

| Sensor | Power Consumption | Low-Light Performance | Frame Rate Support | Manufacturing / Cost | Status |
|---|---|---|---|---|---|
| **CMOS** | Lower | Superior (in modern designs) | Higher — supports fast frame rates | Cheaper to manufacture at large scale, allows integrated on-chip processing | Standard in all modern IP cameras |
| **CCD** | Higher | Historically better at very low light, now surpassed by modern CMOS | Lower | More expensive, harder to scale manufacturing | Legacy — effectively discontinued in new surveillance products |

CMOS won over CCD primarily due to lower power consumption, integrated on-chip signal processing, high frame-rate support, and better suitability for large-scale, low-cost manufacturing — which in turn also drove the low-light performance gains in modern sensors.

## Sensor Size
- Sensor size is measured in **fractional inch format** (e.g. 1/3", 1/2.8", 1/2", 1/1.8", 1/1.2").
- **Bigger fractional number (smaller denominator, e.g. 1/1.2" vs 1/3") = physically larger sensor = more light collected per pixel = better low-light performance.**
- **Analogy:** a large bucket (big sensor) collects far more rainwater (light) than a small cup (small sensor) — in dim conditions, only the big bucket collects enough to be useful.

| Sensor Format | Physical Size | Low-Light Performance | Typical Use |
|---|---|---|---|
| 1/3" | 4.8 × 3.6 mm | Basic | Entry-level indoor |
| 1/2.8" | 6.3 × 4.7 mm | Good | Mid-range indoor/outdoor |
| 1/2" | 6.4 × 4.8 mm | Very Good | Quality outdoor cameras — **minimum recommended for outdoor use in India** given typically poorly-lit night conditions |
| 1/1.8" | 7.2 × 5.4 mm | Excellent | Premium low-light cameras |
| 1/1.2" | 8.8 × 6.6 mm | Outstanding | High-end starlight cameras |

> **Project rule of thumb:** for outdoor cameras in India, always specify a minimum **1/2" sensor** — monsoon nights and poor street lighting make smaller sensors (1/3") unusable for identification purposes.
>
> **Worked example:** a basement car park lit only by emergency lighting — a standard 1/3" sensor produces a near-black image, while a 1/1.8" sensor with an f/1.0 lens produces a clear, usable colour image from the exact same scene. Sensor size and aperture (see [`camera-optics.md`](./camera-optics.md)) work together, not independently.

## Top Component Manufacturers
| Component | Leading Manufacturers |
|---|---|
| Image Sensors / Chips | Sony, OmniVision, ON Semiconductor |
| CPUs | Intel, AMD |
| GPUs | Nvidia, AMD |
| Motherboards | Asus, Gigabyte, MSI, Supermicro |
| Lidar | Hesai, Luminar, RoboSense, Ouster *(see [`11-lidar/lidar-notes.md`](../11-lidar/lidar-notes.md))* |

*(verify/expand — this list is a starting reference, confirm current market leaders per category)*
