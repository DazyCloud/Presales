# Storage & RAID — Reference

## HDD (Hard Disk Drive)
- Slow (compared to SSD)
- Cheap per GB
- Durable for long-term/continuous writes
- **Best for:** backups, CCTV recording storage

## SSD (Solid State Drive)
- Fast
- Expensive (per GB, vs HDD)
- **Best for:** applications, OS, workloads needing quick read/write

## RAID Types
| RAID Level | Definition (short) | When / Why Used |
|---|---|---|
| RAID 0 | Striping — data split across disks, no redundancy | Speed priority, no fault tolerance needed |
| RAID 1 | Mirroring — data duplicated across disks | Redundancy priority, small deployments |
| RAID 5 | Striping with distributed parity | Balance of performance + redundancy (needs 3+ disks) |
| RAID 6 | Like RAID 5, but dual parity | Higher fault tolerance, can survive 2 disk failures |
| RAID 10 | Combination of mirroring + striping | High performance + redundancy, larger deployments |

*(fill in exact definitions/use cases as confirmed)*
