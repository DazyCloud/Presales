# Solution — Metro

## Mandatory Security Features
**Offline search must be available across all zones.**

| Zone | Required Detection / Capability |
|---|---|
| **Ticket area** | Fight detection, offline search |
| **Passage** | Abandoned object detection, vandalism detection, fight detection, fall/slip detection, offline search |
| **Platform** | Line-crossing detection |
| **General / Exit** | Offline search |

## Offline Search — BriefCam
- **Fixed camera range:** 50 m
- **AI behavior approach:** memory-based — **no extra compute required** for the AI processing itself
- **Extra storage IS required** — for metadata used in memory/query triggers
- **How it works:** the system builds a memory of "normal" patterns (time of day, location, count) and flags **unusual behavior** — then classifies it into categories such as: fall, trespassing, loitering, etc.

## Components
- *(to fill in — camera types, ACS, intrusion detection, etc. specific to metro)*

## Integration Notes
- *(to fill in)*

## Constraints Specific to This Vertical
- *(to fill in)*
