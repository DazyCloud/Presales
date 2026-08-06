# Compute Hardware Specs — Reference

## Cores
**Definition:** enables parallel processing — more cores = more simultaneous workloads handled.

| Workload | Typical Core Requirement |
|---|---|
| NVR | 4–8 cores |
| Video Analytics | 16–64 cores |

## Threads
- More threads = more multitasking capability on the same physical core (relevant on VPUs and modern CPUs).

## Clock Speed
- *(definition + typical ranges — to fill in)*
- ANPR-specific base frequency requirements → see [`07-anpr/anpr-design-guide.md`](../07-anpr/anpr-design-guide.md)

## Cache
- On-chip fast memory that reduces latency for frequently accessed data.
- **Types:** *(L1/L2/L3 — to fill in with definitions)*

## RAM
- Current standard: **DDR5**
- *(capacity sizing guidance per workload — to fill in)*

### Memory Module Types
| Module | Description |
|---|---|
| **UDIMM** (Unbuffered DIMM) | Used in desktop PCs. CPU's memory controller talks directly to the DRAM chips — no buffer in between. |
| **RDIMM** (Registered DIMM) | Adds a **register/buffer** between the CPU and the DRAM chips. Path: CPU → register/buffer → DRAM chips. Reduces electrical load on the memory controller. |
| **MRDIMM** (Multiplexed Rank DIMM) | A **server memory module**. Adds a data buffer + multiplexing logic — combines multiple memory data streams/ranks onto a single module. |

## Calibration
**Definition:** the process of adjusting a device so that its output is accurate.

## GPU
Two main types:
- **Integrated GPU** — built into the CPU/motherboard; shares system resources; lower cost, lower performance
- **Dedicated GPU** — separate card with its own resources; used for heavy analytics/AI workloads

## VRAM (Video Memory)
- Dedicated memory on the GPU.
- **Higher VRAM = more concurrent video streams / analytics channels supported.**
