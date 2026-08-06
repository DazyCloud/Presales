# Camera Optics — Reference

## Focal Length vs FOV vs Coverage
| Focal Length | FOV (Field of View) | Best Coverage | Use Case |
|---|---|---|---|
| 2.8 mm | 100–110° | 0–8 m | Indoor overview, ATM, wide-area short range |
| 4 mm | 78–88° | 3–8 m | Door cameras, corridors |
| 6 mm | 55–65° | 5–15 m | Focused outdoor, entrance approach |
| 8 mm | 42–50° | 10–20 m | Outdoor, parking rows |
| 12 mm | 27–35° | 20–40 m | Long-range, perimeter, distant gates |
| 25 mm | 12–17° | 60–100 m | Extreme range — highway, large compounds |
| 50 mm+ | 5–8° | 100 m+ | Extreme long-distance — special surveillance, borders |

> **Relationship is inverse:** short focal length = wide view, less detail per subject; long focal length = narrow view, more detail/magnification. Always confirm the exact figure with a lens calculator (Hikvision/Dahua/Axis/JVSG) for the specific camera resolution — FOV shifts slightly with sensor size too.

## Lens Types

| Type | Description | Best For |
|---|---|---|
| **Fixed** | Focal length permanently set at manufacture | Simple, lowest cost, most reliable — use when distance is fixed/known (e.g. small server room) |
| **Varifocal** | Adjustable focal length (e.g. 2.8–12mm), set manually during install | Requirements not fully known until on-site; camera must be re-focused after adjustment |
| **Motorised Zoom** | Focal length + focus adjusted remotely from the NVR/VMS | High-mounted/multi-storey cameras — saves ladder trips for re-focusing |

## Aperture (F-Number)
**Definition:** the physical opening inside the lens that controls how much light reaches the sensor.
- **Critical rule: lower F-number = wider aperture = more light reaches the sensor.** Think of it like a water pipe — a wider pipe (low f-number) passes more water (light).

| F-Number | Light Level | Use Case |
|---|---|---|
| f/1.0 | Maximum light — 4× more than f/2.0 | Premium low-light cameras |
| f/1.2 – f/1.4 | Excellent | Areas below 5 lux (stairwells, underground parking) |
| f/1.8 – f/2.0 | Good to standard | Well-lit outdoor environments |
| f/2.8 – f/4.0 | Moderate light | Well-lit outdoor use only; **not suitable for low light** |

## Lane Coverage Reference (ANPR / traffic context)
| Scenario | Focal Length |
|---|---|
| Single lane | f 3.8 mm |
| 2-lane (L2) | 7 mm |

> Full ANPR lens/design guidance → see [`07-anpr/anpr-design-guide.md`](../07-anpr/anpr-design-guide.md)
