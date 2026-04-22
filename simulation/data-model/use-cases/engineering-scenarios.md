# Lena Vehicle Data Core — Engineering Use Cases (Scenario-Based)

## Overview

This document defines testable engineering scenarios for the Lena system.

Each scenario demonstrates how deterministic event logging enables system replay, diagnostics, and failure analysis.

---

## Scenario 1 — EV Battery Failure Trace

### Situation
An electric vehicle experiences sudden power loss during operation.

### Problem
Traditional systems cannot fully reconstruct:
- battery state changes
- thermal conditions
- control signals before failure

### Lena Behavior
- Replays full event stream
- Reconstructs battery state timeline
- Identifies triggering event sequence

### Output
- Root cause timeline
- Failure propagation path
- System state reconstruction

---

## Scenario 2 — Autonomous Driving Edge Case

### Situation
Vehicle encounters rare road condition not covered in training data.

### Problem
AI decisions are non-transparent after incident.

### Lena Behavior
- Replays sensor + control events frame-by-frame
- Reconstructs decision chain
- Maps sensor inputs to control outputs

### Output
- Decision trace graph
- Sensor influence mapping
- Behaviour reconstruction timeline

---

## Scenario 3 — ECU Communication Failure

### Situation
One ECU fails to communicate with central system.

### Problem
Missing data breaks system-wide diagnostics.

### Lena Behavior
- Detects missing event sequences
- Reconstructs partial system state
- Flags dependency breakdown

### Output
- Communication failure map
- Dependency graph breakdown
- Partial state reconstruction

---

## Scenario 4 — Post-Crash Forensics

### Situation
Vehicle involved in collision, partial telemetry available.

### Problem
Crash sequence cannot be fully reconstructed.

### Lena Behavior
- Loads last valid event log
- Replays system state until failure point
- Identifies last stable system state

### Output
- Crash timeline reconstruction
- Pre-failure system state snapshot
- Contributing factor map

---

## Scenario 5 — System Overload Simulation

### Situation
Vehicle systems under extreme sensor + compute load.

### Problem
Unclear how system degrades under stress.

### Lena Behavior
- Simulates high-frequency event injection
- Observes system degradation points
- Maps failure thresholds

### Output
- Load threshold curves
- System degradation timeline
- Bottleneck identification

---

## Summary

Lena enables deterministic reconstruction of complex vehicle behaviors across:

- safety systems
- autonomy stacks
- embedded control systems

> Every scenario is replayable. Every failure is traceable.
