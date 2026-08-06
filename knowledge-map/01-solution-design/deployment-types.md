# Deployment Types

There are 5 main deployment types for a solution:

1. **On-PC**
2. **On-Cam**
3. **On-Server**
4. **On-Edge**
5. **On-Premises**

## On-Cam

**Pros:**
- Low cost
- Low average bandwidth
- Good for people/vehicle detection
- Easy integration for live monitoring
- Easy search
- Low power
- Fewer hardware types needed

**Cons:**
- CMS/central integration not always possible
- Camera replacement cost (analytics tied to camera hardware)

## On-PC

**Pros:**
- Advanced analytics possible
- No extra hardware needed (beyond the PC)
- Cost benefit at scale

**Cons:**
- Hardware limitations
- Dependent on camera's processing/streaming capability

## On-Server

Analytics/processing runs centrally on a dedicated server (rack-mounted, typically in a server room or data center) rather than on the camera or a local PC. Cameras stream raw video to the server; the server does the heavy lifting (VA, FRS, ANPR, etc.).

**Pros:**
- Centralized management — one place to configure, monitor, and troubleshoot analytics
- Scalable processing power — add GPUs/CPU or scale out with more servers as camera count grows
- Best suited for heavy, multi-channel analytics (FRS galleries, ANPR across many lanes, VA across large sites)
- Easier software/firmware updates — pushed once, centrally
- Can support clustering/failover (HA) for critical sites

**Cons:**
- Single point of failure if not built with redundancy (RAID, HA cluster, backup power)
- Higher upfront hardware cost (server chassis, GPU cards, enterprise storage)
- Needs a proper server room — power, cooling, UPS, physical security
- Full-resolution video still needs to reach the server, so backbone network bandwidth must be sized accordingly

**Notes:**
- This is the classic **NVR/VMS + analytics server** model used in most mid-to-large installations (banks, malls, campuses).
- Server sizing (cores, GPU, VRAM, storage) → see [`03-hardware/compute-specs.md`](../03-hardware/compute-specs.md) and [`03-hardware/hardware-requirements.md`](../03-hardware/hardware-requirements.md)

## On-Edge

Analytics runs on a small compute device placed close to the cameras — e.g. an NVIDIA Jetson box, an industrial edge PC, or a PoE-powered edge appliance serving a cluster of cameras at one location — rather than on a central server or inside the camera itself. Distinct from **On-Cam**, where the analytics engine is embedded in the camera's own chip/firmware.

**Pros:**
- Low latency — real-time detection/alerting without a round trip to a central server
- Reduces backbone bandwidth — only metadata/events/thumbnails (not full video) need to travel to the central VMS
- Resilient to network/internet interruption — local site keeps working even if the link to HQ drops
- Scales linearly per site — add an edge box as new locations come online, without re-sizing a central server

**Cons:**
- More devices to manage/maintain — one edge box per site (or per camera cluster) instead of one central server
- Hardware cost adds up at scale (many small boxes vs one big server)
- Software/firmware updates must be pushed to many distributed devices — harder to keep consistent
- Centralized troubleshooting/monitoring is harder than a single server room

**Notes:**
- Common for **multi-site rollouts** (retail chains, branch banking, highway/toll stretches) where each site must keep functioning independently.
- Sits between On-Cam (fully embedded) and On-Server (fully centralized) on the processing-location spectrum.

## On-Premises

This describes **where the overall solution is hosted** (client's own site/campus) as opposed to the **cloud** — a different axis from On-Cam/On-PC/On-Edge/On-Server, which describe *where analytics processing happens*. A solution can be On-Server *and* On-Premises at the same time (most common combination in India for regulated sectors).

**Pros:**
- Full data control and ownership — video/data never leaves client premises (important for data sovereignty, RBI/STQC compliance, defense/govt sites)
- No recurring cloud subscription cost — CAPEX-heavy model instead of ongoing OPEX
- No dependency on internet uptime for local viewing/recording/alerting
- Easier to satisfy regulatory/compliance requirements (e.g. **STQC:ER:01**, data-localization mandates)

**Cons:**
- Higher upfront CAPEX (servers, storage, licensing, server room)
- Client needs in-house IT/maintenance capability (or an AMC/SI to support it)
- Harder to scale quickly — new hardware must be procured and installed vs simply increasing a cloud tier
- Multi-site central visibility needs extra work (VPN/WAN links, federated VMS) compared to a cloud-native platform
- Physical security and uptime of the server room become the client's own responsibility

**Notes:**
- Opposite/complement is **cloud-hosted VMS** (e.g. Verkada-style, cloud-native platforms) — video/analytics processed and stored off-site by the vendor.
- CAPEX vs OPEX trade-off → see [`05-glossary/basic-definitions.md`](../05-glossary/basic-definitions.md#business-terms)

## Summary Comparison

| Deployment Type | Where Analytics Run | Typical Latency | Bandwidth to Center | Best Fit |
|---|---|---|---|---|
| On-Cam | Inside the camera | Lowest | Minimal (events only) | Small sites, budget-conscious, simple detection |
| On-PC | Local PC/workstation | Low | Local only | Single-site, small camera count, no dedicated server room |
| On-Edge | Nearby edge appliance | Low | Low (metadata/events) | Multi-site rollouts needing local resilience |
| On-Server | Central server/data center | Medium (network dependent) | High (full video streams) | Large single-site or campus with heavy analytics |
| On-Premises | *(hosting location, not a processing tier)* | — | — | Regulated/data-sovereignty-sensitive clients |
