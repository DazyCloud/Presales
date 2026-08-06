# Camera Components

> Camera-specific parts stay here (in the camera folder) — not in `03-hardware/`, which covers system/server-side hardware only.

## Core Components
- **Lens** — see [`camera-optics.md`](./camera-optics.md) for focal length/FOV/aperture detail
- **Sensor** — common sizes: **1/2"** and **1/3"** — see [`image-sensors.md`](./image-sensors.md)
- **Image Signal Processor (ISP)** — chip that converts the raw sensor signal into a usable image (handles WDR, noise reduction, AWB/AGC/BLC — see [`camera-specifications.md`](./camera-specifications.md))
- **Encoder** — compresses the processed video into H.264/H.265 for transmission/storage (see [`camera-specifications.md`](./camera-specifications.md))
- **Transmitter** — the network interface (Ethernet PHY chip) that packages the encoded video into IP packets and sends it out over the Cat5e/Cat6 cable to the switch/NVR; on a PoE camera this same port also receives power from the PoE switch.
- **IR Illuminator / White-Light LED** — supplemental light source for night vision (see [`camera-specifications.md`](./camera-specifications.md) → Night Vision/IR)
- **Housing** — physical enclosure; determines IP/IK rating (ingress/impact protection) — see [`05-glossary/ratings-and-standards.md`](../05-glossary/ratings-and-standards.md)
- **microSD Slot** — optional on-board edge storage, independent of the NVR (backup recording if network fails)

## Form Factor
**Definition:** the physical characteristic (size/shape) of a product — relevant when comparing cameras or components for fit/mounting.
