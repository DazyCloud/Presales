# Video Analytics — General Notes

> For the 7-layer pipeline, edge/server/hybrid architecture, performance metrics, deployment methodology, and common mistakes, see [`video-analytics-deployment-guide.md`](./video-analytics-deployment-guide.md).

## Fall Detection — Working Principle
Detected as a **sequence of posture changes**:
1. Loss of balance
2. Fast descent
3. Lying position

## Fight Detection — Working Principle
Detected as a **repeated, high-velocity, opposing-direction movement** pattern between subjects.

## Fire & Smoke Detection — Working Principle
Combines 3 techniques as a dedicated module:
- Color model
- Motion analysis
- Texture analysis

## What Determines VA Accuracy
- Training / engine learning quality (how well the model is trained)
- Fire/smoke detection capability (check this specifically when evaluating any new VA OEM)

## Event Triggering
- An **event** is generally defined as something occupying **~10% of the frame** — once a detected object/change crosses that threshold, the system **triggers** an event.

## PSIM / CNC
- **PSIM** (Physical Security Information Management) — used with **CNC** for intrusion detection integration/correlation across systems.

## Performance Factors (Remember: "FOV, Lens, Mounting Height, ROI")
Video analytics performance depends heavily on:
- **FOV** (Field of View)
- **Lens** (type/focal length)
- **Mounting height**
- **ROI** (Region of Interest) — how it's configured

## Product Selection
Choose a VA product based on required features vs performance — see the site-specific [`13-solutions/`](../13-solutions/) files for how this plays out per vertical.
