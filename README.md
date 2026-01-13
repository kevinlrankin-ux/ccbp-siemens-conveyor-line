# CCBP Siemens Conveyor Line (5-Zone)

This repository provides a **field-ready** Siemens TIA Portal control architecture for a multi‑zone conveyor line, governed by the **Consciousness–Capability Boundary Project (CCBP)**.

## What This Is
- A **spec-first** industrial automation template
- Target platform: **Siemens S7‑1500**, **TIA Portal v18**
- Language: **Structured Text (SCL)**
- Sequencing: **downstream‑first start** / **upstream‑first stop**
- HMI policy: **NO_INST_DB** (WinCC reads **public status DBs only**)

## What This Is Not
- Not executable outside Siemens TIA Portal
- Not a safety-certified (F‑CPU) implementation
- Not a replacement for commissioning, validation, or site safety requirements

## Repository Contents
- `spec/` — Authoritative CCBP control specification (YAML)
- `plc/` — SCL artifacts (UDT/FB stubs + OB1 skeleton), DB plans
- `hmi/` — WinCC faceplate binding contracts (NO_INST_DB)
- `alarms/` — Alarm catalog (YAML)
- `tests/` — FAT/SAT tests (YAML)
- `docs/` — Commissioning checklist + architecture notes

## Design Principles
- **Safety dominance** via `xEStopOK` gating (outputs forced FALSE on E‑Stop)
- **Bounded reset** (no auto-reset; reset only when safe)
- **Deterministic precedence** (first-out/ordering is explicit)
- Separation of **spec**, **execution**, and **presentation**
- No anthropomorphic or agentic assumptions

## Quick Start
1. Review `spec/conveyor_line_5zone.yaml`
2. Import SCL artifacts under `plc/` into your TIA Portal project
3. Create DBs per `plc/db/DB_PLAN.md`
4. Integrate `plc/ob/OB1_CL01.scl`
5. Bind WinCC using `hmi/faceplates.md` (NO_INST_DB)
6. Execute FAT/SAT tests in `tests/fat_sat_tests.yaml`

## License
Licensed under the Apache License 2.0. See `LICENSE`.
