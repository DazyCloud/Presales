# Decision Framework — Choosing a Deployment Type

Before finalizing a solution, ask the right questions based on the application.

## Process
1. Ask: what is the application? (e.g., ANPR, access control, monitoring)
2. Match application to deployment type based on need.

### Examples
- **ANPR for parking** → On-Edge (fine for access control use case)
- **ANPR for cities** → On-PC (city-scale, camera has built-in analytics isn't enough)
- Camera has built-in analytics → On-Cam is viable

## Why would a client want On-PC over On-Cam?
- Their existing cameras may not be compatible (no onboard analytics) for the analytics needed
- On-PC allows advanced analytics regardless of camera's native capability

## Range Consideration
- On-PC based capture range: up to ~230m
- On-Cam based capture range: up to ~100m
