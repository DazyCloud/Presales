# Basic Definitions (Quick Reference)

Short, easy definitions with examples — for fast revision.

- **I-frame** (Intra-frame / key frame) — a full, self-contained image frame in a compressed video stream; every other frame (P/B-frames) only stores the *difference* from the nearest I-frame. Example: if network drops a P-frame, playback glitches until the next I-frame arrives — this is why "I-frame interval" (GOP length) matters for recording/search: shorter interval = better seek accuracy but bigger file size.
- **Encoder types** — device/software that compresses raw video into a storable/streamable format.
  - **Camera-side encoder** — built into the IP camera; compresses video before it leaves the device (H.264/H.265)
  - **Server-side encoder (transcoder)** — re-encodes an existing stream, e.g. for a lower-bitrate substream or a different codec for a specific client
  - **Hardware encoder** — dedicated chip (ASIC/SoC) does the compression; low CPU load, used in cameras and NVRs
  - **Software encoder** — CPU/GPU does the compression via software (e.g. x264/x265 libraries); flexible but resource-heavy
- **NAC (Network Access Control)** — controls which devices can access a network
- **SAN (Storage Area Network)** — dedicated high-speed network for shared storage
- **MAC address** — unique hardware identifier for a network interface
- **Subnets** — division of a network into smaller logical segments
- **Protocols** — communication rules, e.g. **MQTT** (lightweight pub/sub messaging protocol, common in IoT/camera systems)

## Common Ports Reference

Useful for firewall rules, troubleshooting connectivity, and RFP technical compliance sheets.

| Port | Protocol | Purpose |
|---|---|---|
| 80 | HTTP | Unencrypted web/camera admin interface |
| 443 | HTTPS | Encrypted web/camera admin interface, VMS web clients (TLS/SSL) |
| 20 / 21 | FTP | File transfer (control on 21, data on 20) — often used for camera snapshot/clip upload |
| 22 | SSH | Secure remote shell/CLI access to servers, switches |
| 23 | Telnet | Unencrypted remote CLI — **should be disabled** on cameras/NVRs for security |
| 25 | SMTP | Outgoing email (alert notifications from VMS/NVR) |
| 53 | DNS | Domain name resolution |
| 67 / 68 | DHCP | Automatic IP address assignment (server/client) |
| 123 | NTP | Network Time Protocol — time sync, critical for accurate video timestamps/forensic search |
| 161 / 162 | SNMP | Device monitoring/management; 162 for traps (alerts) |
| 389 / 636 | LDAP / LDAPS | Directory services — VMS user auth against Active Directory |
| 554 | RTSP | Camera-to-VMS streaming session control |
| 1883 / 8883 | MQTT | Lightweight pub/sub messaging (unencrypted / TLS) |
| 1935 | RTMP | Streaming push, e.g. cloud VMS, YouTube Live |
| 3702 | WS-Discovery | Used by **ONVIF** for auto-discovery of cameras on the LAN |
| 5060 / 5061 | SIP | VoIP/intercom session setup (unencrypted / TLS) |

> HTTP vs HTTPS is a good default technical-compliance line item in RFPs — always require HTTPS on camera/NVR web interfaces, never HTTP-only.

## More Networking Terms
- **DHCP (Dynamic Host Configuration Protocol)** — automatically assigns IP addresses to devices on a network, avoiding manual configuration on every camera.
- **NAT (Network Address Translation)** — translates private internal IPs to a public IP for internet access; used when exposing a VMS/NVR externally (though direct exposure is discouraged — see cybersecurity notes).
- **VLAN (Virtual LAN)** — logically separates a physical network into isolated segments; best practice to put all cameras/NVRs on a dedicated surveillance VLAN, separate from the corporate IT network.
- **Gateway** — the network device (usually a router) that connects a local network to another network/the internet.
- **Subnet Mask** — defines which part of an IP address is the network portion vs the host portion (e.g. 255.255.255.0 = /24).
- **Latency** — the delay between an action and its effect being observed (e.g. camera capture → alert on screen). Lower is better for live monitoring/PTZ control.
- **Jitter** — variation in latency over time; high jitter causes choppy/stuttering video even if average latency is low.
- **Throughput / Bandwidth** — the actual/maximum data transfer rate of a link, usually in Mbps/Gbps.
- **Failover** — automatic switch to a backup system/server when the primary fails, to maintain uptime.
- **Redundancy** — having duplicate critical components (servers, storage, power, network paths) so a single failure doesn't cause downtime.
- **MTBF (Mean Time Between Failures)** — average expected time a device runs before it fails; higher = more reliable. Common spec for HDDs, servers, PSUs.
- **MTTR (Mean Time To Repair)** — average time taken to fix/replace a failed component and restore service.
- **Firmware** — low-level software embedded in a hardware device (camera, switch, NVR) that controls its core operation; distinct from application software.
- **Middleware** — software layer that connects/integrates two systems that wouldn't otherwise talk to each other (e.g. connecting a VMS to an access-control system).
- **Metadata** — data *about* the video/data, not the video itself (e.g. timestamp, object type, bounding box coordinates, plate number) — this is what edge AI typically sends back to save bandwidth.
- **ROI (Region of Interest)** — a defined area within a camera's field of view where analytics/detection is applied, ignoring the rest of the frame.
- **PTZ (Pan-Tilt-Zoom)** — a camera's ability to be remotely panned, tilted, and zoomed; also refers to that camera type.

*(expand each with 1-2 line definition + example as notes come in)*

## Resolution Reference (720p → 4K)
| Name | Pixel Resolution |
|---|---|
| 720p (HD) | 1280 x 720 |
| 1080p (Full HD) | 1920 x 1080 |
| 2K | 2560 x 1440 |
| 4K (UHD) | 3840 x 2160 |

*(fill in exact numbers for 2K/4K variants used by camera vendors if they differ)*

## Business Terms
- **CAPEX (Capital Expenditure)** — spending on long-term physical assets (e.g. buying cameras, servers, hardware outright).
- **OPEX (Operating Expenditure)** — ongoing/recurring spending to run the business (e.g. subscription licenses, cloud storage fees, maintenance contracts).

## Electronics / Hardware Terms
- **SPI (Serial Peripheral Interface)** — communication interface using a **controller–peripheral architecture** (1 controller can talk to many peripherals).

## Integration Terms
- **API** — used for **application-to-application** communication.
- **SDK** — used for **hardware** integration.

## Biometric / FRS Terms (Quick Reference)
- **Embedding** — numerical vector representing a face, used for comparison.
- **Enrollment** — process of creating and storing a person's face template.
- **Gallery** — collection of enrolled templates used for matching.
- **Watchlist** — special gallery for alerting/surveillance (persons of interest).
- **Liveness** — check that a presented face is a real live person (not photo/video/mask).
- **Capture Zone** — physical area where the face is expected to be captured correctly (known distance, pose, lighting).
- **Threshold** — score level above which the system calls a match. Higher = stricter = fewer false accepts.
- **Quality Gate** — rule that blocks poor-quality images from enrollment/matching.
- **Forensic Search** — searching recorded video/indexed events for a target person after the fact.
