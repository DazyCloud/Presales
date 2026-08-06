# Detection / Model Metrics

Metrics used to evaluate how well a detection/recognition model (VA, FRS, ANPR) performs — useful for reading vendor spec sheets and writing RFP compliance criteria.

## Confusion Matrix Basics (foundation for everything below)

| Term | Meaning |
|---|---|
| **TP (True Positive)** | Model correctly detected/matched something that was actually there |
| **TN (True Negative)** | Model correctly said "nothing here" when there was nothing |
| **FP (False Positive)** | Model flagged something that wasn't actually there (false alarm) |
| **FN (False Negative)** | Model missed something that was actually there (missed detection) |

## Core Metrics

**Precision** — of everything the model *flagged* as positive, how much was actually correct.
- **Formula:** Precision = TP / (TP + FP)
- **When to use:** when false alarms are costly (e.g. an intrusion alert that pages a guard every night for a stray cat — low precision = alert fatigue).
- **Example:** System raises 100 intrusion alerts; 90 are real intrusions, 10 are false alarms → Precision = 90/100 = 0.90

**Recall (Sensitivity / Detection Rate)** — of everything that was *actually there*, how much did the model catch.
- **Formula:** Recall = TP / (TP + FN)
- **When to use:** when missing an event is unacceptable (e.g. perimeter breach, a wanted-person match) — you'd rather tolerate more false alarms than miss the real thing.
- **Example:** 100 real intrusions occurred; system detected 85 of them → Recall = 85/100 = 0.85

**F1 Score** — harmonic mean of Precision and Recall; a single number balancing both.
- **Formula:** F1 = 2 × (Precision × Recall) / (Precision + Recall)
- **When to use:** comparing overall model quality when both false alarms and missed detections matter, and you want one comparable number across vendors.
- **Example:** Precision = 0.90, Recall = 0.85 → F1 = 2×(0.90×0.85)/(0.90+0.85) ≈ 0.874

**Accuracy** — overall proportion of correct predictions (positive and negative combined).
- **Formula:** Accuracy = (TP + TN) / (TP + TN + FP + FN)
- **Caution:** misleading on imbalanced data — e.g. "intrusion" events are rare, so a model that predicts "no intrusion" 99.9% of the time can show high accuracy while catching almost nothing. Prefer Precision/Recall/F1 for surveillance use cases.

## Biometric / Matching Metrics (FRS, ANPR)

**FAR / FMR (False Acceptance Rate / False Match Rate)** — rate at which the system wrongly matches two *different* people/plates as the same.
- **Formula:** FAR = False Matches / Total Impostor Comparisons
- **Example:** Security-critical sites (banks, defense) want FAR as close to 0 as possible even if it costs some Recall.

**FRR / FNMR (False Rejection Rate / False Non-Match Rate)** — rate at which the system wrongly fails to match the *same* person/plate.
- **Formula:** FRR = False Non-Matches / Total Genuine Comparisons
- **Example:** A watchlist match system with high FRR will let known persons of interest walk past undetected.

**EER (Equal Error Rate)** — the point where FAR = FRR; used as a single comparable number when evaluating biometric engines. **Lower EER = better overall accuracy.**

**Threshold** — the score cutoff above which the system calls something a match. Raising it lowers FAR but raises FRR (and vice versa) — this is the FAR/FRR trade-off knob.

## Object Detection Metrics (Video Analytics)

**IoU (Intersection over Union)** — how well a model's predicted bounding box overlaps with the actual (ground-truth) box.
- **Formula:** IoU = Area of Overlap / Area of Union
- **Example:** IoU ≥ 0.5 is a common threshold to count a detection as "correct" in benchmark evaluations.

**mAP (mean Average Precision)** — the standard single-number benchmark for object-detection model quality; averages precision across all object classes and confidence thresholds (via the Precision-Recall curve).
- **When to use:** comparing two VA/object-detection engines against a common benchmark dataset (e.g. COCO) — higher mAP = generally better detector.

**False Alarm Rate (FAR — operational, not biometric)** — in a VA/perimeter context, number of false alerts per unit time (e.g. per camera per day). A key line item in RFP acceptance criteria (e.g. "≤ 1 false alarm per camera per 24 hours").

## System Performance Metrics (not accuracy, but often confused with it)

**Latency** — time between an event occurring and the system generating a result/alert. Measured in ms; critical for real-time use cases (PTZ auto-tracking, live alerting).

**Throughput** — number of inferences (detections/matches) the system can process per second; determines how many camera channels a given server/edge box can support.

**FPS (as a model-serving metric)** — frames per second the analytics engine can actually process, which may be lower than the camera's captured FPS if the model is compute-bound — a common gap between "camera spec" and "real-world analytics performance" to watch for during PoC/testing.

*(Add vendor-specific benchmark numbers here as PoC/testing data comes in — e.g. FRS engine X: FAR 0.001% @ FRR 1% on internal test set.)*
