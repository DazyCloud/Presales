# Networking Basics (Detailed Quick-Revision)

Not just basics — detailed enough to not forget. 1-2 lines per point, but all points covered.

## Switches
- Switch types (managed/unmanaged, PoE, L2/L3, SFP/SFP+) — full detail → [`03-hardware/networking-hardware.md`](../03-hardware/networking-hardware.md)

## Memory
- **RAM types**, incl. **ECC RAM** (Error-Correcting Code RAM — detects/corrects memory errors, used in servers)
- Base clock / frequency — relevance to performance
- Full compute specs (cores, threads, cache, GPU/VRAM) → [`03-hardware/compute-specs.md`](../03-hardware/compute-specs.md)

## Storage
- **RAID types** — detailed list (RAID 0, 1, 5, 6, 10, etc.) with 1-2 line explanation each → [`03-hardware/storage-and-raid.md`](../03-hardware/storage-and-raid.md)

## Protocols

### Transport Protocols
| Protocol | Definition | Behavior | Use Case |
|---|---|---|---|
| **TCP** | Connection-oriented | Packets delivered in order — reliable but slower | Camera web interface, ONVIF, VMS channel |
| **UDP** | Connectionless | "Speed courier" — fast, no delivery guarantee | Continuous live video streams, multicast streaming |

> For a well-managed local LAN, **RTSP** is the go-to streaming protocol.

### Streaming Protocols
| Protocol | Port | Description | Use Case |
|---|---|---|---|
| **RTSP** | 554 | Remote control of streaming (start/stop/seek via URL) | Camera-to-VMS streaming setup |
| **RTP** | — | Real-time Transport Protocol — carries the actual video/audio packets; runs over UDP | Underlying transport for live streams |
| **RTMP** | 1935 | Messaging-based protocol that pushes a stream; needs CBR | e.g. YouTube Live, cloud VMS |
| **WebRTC** | — | Real-time communication protocol | Modern cloud VMS pattern |
| **GB/T 28181** | — | Chinese technical framework/standard for video surveillance networks — converts a local (LAN) stream into a regional/national-level stream | Interoperability with China-standard surveillance networks |
| **SRT** (Secure Reliable Transport) | — | Low-latency transmission protocol | Used where low-latency, secure transport is required |

### Media / Device-Control Protocol Layers
- **Media streaming (SIO)** — video encoded to PS (Program Stream) packets, carried over RTP/RTCP
- **Device control** — **MANSCDD** and **MANSRTSP** — used for remote device control / actuation with low-latency transmission

### ONVIF (Interoperability Standard)
| Profile | Purpose |
|---|---|
| **Profile S** | Basic streaming |
| **Profile T** | Advanced streaming |
| **Profile G** | Edge storage |
| **Profile M** | Analytics |
| **Profile A / C / D** | Access control |

### Other Protocols
- **FTP** — File Transfer Protocol
- **SIP** (Session Initiation Protocol) — used for setting up/managing communication sessions (e.g. VoIP, some intercom/audio integrations)
- **IGMP** (Internet Group Management Protocol) — used by hosts/routers to manage multicast group membership
- **IGMP Snooping** — a switch listens in on IGMP traffic to only forward multicast streams to ports that actually requested them (avoids flooding the whole network) — important for efficient camera multicast
- **MQTT** — works on a **publish-subscribe model** (devices publish to a topic, subscribers receive updates on that topic)

### Communication Protocols — Full Forms (Quick Reference)
| Protocol | Full Form |
|---|---|
| ONVIF | Open Network Video Interface Forum |
| BACnet | Building Automation and Control Networks |
| Modbus | *(protocol name, not an acronym)* |
| MQTT | Message Queuing Telemetry Transport |
| OPC (UA) | Open Platform Communications (Unified Architecture) |
| SNMP | Simple Network Management Protocol |
| SIP | Session Initiation Protocol |
- OSI layer mapping — which component/protocol belongs to which layer

### VPN / WAN
- **VPN types** — *(to fill in)*
- **MPLS** — *(to fill in)*
- **PIL** — *(to fill in — confirm what this stands for)*

## Cabling
- Cat5, Cat6, fiber (single-mode/multi-mode) — full detail → [`03-hardware/networking-hardware.md`](../03-hardware/networking-hardware.md)
- **Cat5e / Cat6** — both support a max run of **100 m**

## Security
- **Firewalls** — traffic filtering
- **ARP** (Address Resolution Protocol) — maps IP to MAC address
- **STP** (Spanning Tree Protocol) — prevents network loops in switched networks with redundant paths
- **NFC** (Near Field Communication) — used to read an encrypted chip inside an ID card/badge
- **ACL** (Access Control List) — rules controlling traffic access

## Traffic Types
- **Broadcast** — one-to-all (every device on the network receives it)
- **Multicast** — one-to-many, but only to devices that have subscribed to the stream (more efficient than broadcast for video)

### Camera Transmission: Unicast vs Multicast
Cameras transmit video using one of two modes:

- **Unicast** — one dedicated stream per receiving client (bandwidth scales with number of viewers)
- **Multicast** — single stream shared by multiple subscribed clients (bandwidth-efficient for many simultaneous viewers, e.g. control rooms)

**Multicast support depends on where it's implemented:**
| Side | OEM that supports it |
|---|---|
| Server side | NX, Milestone |
| Camera side | **Genetec** (preferred) |

> Keep this OEM preference in mind when proposing a solution that requires multicast — it directly affects which VMS/camera OEM to select.

**Throughput terms:**
- **In-throughput** — incoming bandwidth/data rate into a device (e.g. NVR/server receiving camera streams)
- **Out-throughput** — outgoing bandwidth/data rate from a device (e.g. server streaming to clients/viewers)

### Stream Bitrates (reference)
| Stream Type | Bitrate |
|---|---|
| Substream | 150 Mbps |
| Mainstream | 300 Mbps |

*(Note: these figures are from raw notes — confirm whether they're per-camera or aggregate, as typical single-camera substreams are usually far lower; likely meant as example/reference values for a specific deployment — verify before reuse.)*

## Other
- **Ping** — network reachability/latency test tool

*(each bullet to be expanded to 1-2 lines with example as revision notes are added)*
