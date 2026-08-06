# Camera Specifications — Reference

- **Encoder** — device/type used to process video streams
- **Lens Types** — see [`camera-optics.md`](./camera-optics.md)
- **Ping** — used for network reachability check on cameras

### SD Card Classes (relevant for on-board edge storage)
| Class | Minimum Write Speed | Notes |
|---|---|---|
| Class 10 | 10 MB/s | Minimum acceptable for continuous video recording |
| UHS-I (U1) | 10 MB/s | Same floor as Class 10, newer bus interface |
| UHS-I (U3) | 30 MB/s | Recommended for higher-bitrate H.265 streams |
| V30 (Video Speed Class) | 30 MB/s | Explicit video-recording rating — preferred spec line for camera edge storage |
| Endurance / High-Endurance cards | — | Purpose-built for 24×7 continuous overwrite (unlike consumer cards meant for occasional photo/video capture) — **always specify endurance-rated cards for CCTV edge storage**, not standard consumer microSD |

> Reference: at 2 Mbps (H.265), a 128GB card holds roughly ~7 days of continuous recording.

### Video File Formats (container formats — distinct from the codec/compression inside them)
| Format | Notes |
|---|---|
| **MP4** | Most common export/playback format from VMS/NVR clips |
| **AVI** | Older container, still used by some legacy NVR exports |
| **MKV** | Flexible container, supports multiple audio/subtitle tracks — less common in CCTV exports |
| **Proprietary VMS export (.exe/.g64/etc.)** | Some VMS vendors export a self-playing proprietary format with embedded watermark/chain-of-custody data for forensic/legal use |

### Compression Types (Codecs)
| Codec | Type | Efficiency | Best For |
|---|---|---|---|
| **MJPEG** | Intra-frame (every frame compressed independently) | Very low — large files | Legacy, low-latency use only |
| **H.264 (AVC)** | Inter-frame (stores only differences between frames) | High — near-universal support | Current safe-choice baseline for all systems |
| **H.265 (HEVC)** | Inter-frame | ~50% better than H.264 at the same visual quality | Recommended default for all new deployments |
| **H.265+** | Vendor-enhanced H.265 (Hikvision/Dahua proprietary) | Up to 70–80% better than H.264 | Storage-constrained large projects — requires vendor-compatible NVR/VMS |

> H.265 encoding needs 3–5× more processing power than H.264 — factor this into camera/NVR compute sizing, not just storage sizing.

### Encoding/Bitrate Control Types
See **Bitrate** section below (CBR/VBR/CVBR/ABR) — these define *how* the encoder allocates bits over time, separate from the codec (H.264/H.265) which defines *how* compression itself works.

## FPS (Frames Per Second)
**Definition:** number of still images captured per second. Higher FPS = smoother video.

| Use Case | FPS |
|---|---|
| Static scene | 1–5 fps |
| Default / general | 25 fps |
| Standard surveillance | 25 fps |
| Ultra-smooth (fast motion) | 60 fps |

> Special note: **FPS for ANPR** needs to be higher for fast-moving vehicles (free-flow).

## Bitrate
**Definition:** amount of video data transmitted per second (kbps/Mbps).
> Higher bitrate = better quality, but higher storage and bandwidth consumption.

| Type | Description |
|---|---|
| **CBR** (Constant Bitrate) | Fixed rate — good for managed LAN/WAN (predictable bandwidth) |
| **VBR** (Variable Bitrate) | Rate varies with scene complexity |
| **CVBR** (Constrained VBR) | VBR with an upper cap — used for managed LAN/WAN where bandwidth must stay predictable |
| **ABR** (Adaptive Bitrate) | Adapts automatically to network conditions |

## Stream Types
| Stream | Typical Resolution | Use Case |
|---|---|---|
| **Mainstream** | Full HD | Live viewing, NVR recording |
| **Substream** | 720p | Mobile viewing |
| **Third stream** | Configurable | Cloud streaming |

## Resolution — Purpose-Based Requirement (Pixel Density)
- **Pixel density** = number of pixels covering the target at the target distance.
- **Resolution** = how many pixels make up the captured image.

| Purpose | Pixel Density Required |
|---|---|
| Detect presence | 25 px/m |
| General/standard surveillance | 2 MP (standard) |
| Outdoor use | 8 MP (4K) |
| Detect behavior | 63 px/m |
| Recognize a face | 125 px/m |
| Identify an unknown face | 250 px/m |
| Read a license plate | 800 px/m |

## Shutter Speed
**Definition:** the sensor activates electronically to control exposure duration per frame (electronic shutter).

| Subject Motion | Shutter Speed |
|---|---|
| Static subject | 1/25 s |
| Walking person | 1/125 s |
| Running person | 1/250 s |
| Moving vehicle | 1/500 s |
| Fast-moving vehicle | 1/1000 s |

> Faster shutter speed = less light reaches the sensor = less motion blur, but darker image in low light. Trade-off between blur and exposure.

## WDR (Wide Dynamic Range)
| Type | Description |
|---|---|
| **True WDR** | High cost; minimum 120dB; achieved via multi-exposure hardware + ISP fusion |
| **Digital WDR** | Software-based contrast enhancement; lower cost; **not suitable for night/low-light vision** |

## Night Vision / IR

| Technology | Output at Night | Visible? | Best Use |
|---|---|---|---|
| Standard IR (850nm) | Black & White | Faint red glow | Standard outdoor cameras |
| IR (940nm) | Black & White | Invisible | Covert perimeter |
| **Smart IR** | B&W, auto-adjusted intensity (no overexposure) | Faint or invisible | Entries, corridors — **always specify for entry-point cameras** |
| Full-Colour (White-Light) | Full Colour | Very visible | Entries, retail exteriors — acts as visible deterrent, higher power draw |
| Dual-Light | B&W or Colour (switchable) | Switchable | Perimeter with alarm response — IR by default, switches to white-light on alarm trigger |
| Starlight / Ultra-Low-Light | Colour, no supplemental LEDs | No supplemental light | Premium covert, heritage sites — needs large sensor (1/1.8"+) + wide aperture (f/1.0–f/1.4), works down to ~0.001 lux |

> **Critical rule:** always specify **Smart IR** at entry points where a person walks close to the camera (0.5–1m) — standard fixed-intensity IR will white-out/overexpose faces at close range.
- **Bullet camera IR range:** typically 40–100 m

## Camera Selection Checklist
When selecting a camera, check/ask:
- Coverage area needed
- Mounting location
- Environment (indoor/outdoor, lighting conditions)
- Analytics requirements
