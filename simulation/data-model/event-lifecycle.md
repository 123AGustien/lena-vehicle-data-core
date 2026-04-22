# Lena Vehicle Data Core — Event Lifecycle Rules

## Overview

This document defines how events move through the Lena system from creation to replay.

It ensures deterministic behavior across all vehicle data processing layers.

---

## Core Principle

> "Events are never destroyed, only transformed through system layers."

---

## 1. Event Lifecycle Stages

### Stage 1 — Capture
Events are generated from vehicle systems:

- Sensors
- ECUs
- Control modules
- System state monitors

---

### Stage 2 — Validation
Each event is validated for:

- Timestamp correctness
- Schema compliance
- Source authenticity
- Context completeness

Invalid events are flagged, not deleted.

---

### Stage 3 — Normalization
Events are converted into a standard format:

- Unified schema structure
- Standardized metadata
- Consistent timestamp format

---

### Stage 4 — Storage
Events are stored in an immutable log:

- Append-only system
- No overwrite allowed
- Ordered by timestamp

---

### Stage 5 — Indexing
Events are indexed for:

- Fast retrieval
- System correlation
- Cross-component analysis

---

### Stage 6 — Replay / Simulation
Events can be replayed to reconstruct system behavior:

- Chronological execution
- State reconstruction
- Failure reproduction

---

## 2. Event Integrity Rules

- No event can be deleted
- No event can be modified after storage
- All changes must be represented as new events
- System state is always derived, never stored directly

---

## 3. Failure Handling Model

If an event is corrupted or incomplete:

- It is marked as `degraded`
- System continues processing
- Correlation engine attempts reconstruction

---

## 4. Determinism Requirement

The system must guarantee:

> Same input event stream = same system output state

---

## 5. Integration

This lifecycle model supports:

- Simulation Engine
- Observability Layer
- Failure Analysis System

It is a foundational component of the Lena Vehicle Data Core architecture.
