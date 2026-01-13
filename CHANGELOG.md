# Changelog
All notable changes to this project will be documented in this file.

This project follows a simple, inspectable versioning approach:
- MAJOR: breaking interface/spec changes
- MINOR: additive features, new modules
- PATCH: fixes, clarifications, non-breaking improvements

## [v1.0.0] - 2026-01-13
### Added
- Spec-first Siemens conveyor line template (5 zones) governed by CCBP
- Authoritative control spec: `spec/conveyor_line_5zone.yaml`
- PLC implementation artifacts:
  - `plc/ob/OB1_CL01.scl`
  - DB plan guidance: `plc/db/DB_PLAN.md`
- HMI policy: **NO_INST_DB**
- Alarm catalog and FAT/SAT tests
- Commissioning checklist and architecture notes
- Licensing: Apache-2.0 + NOTICE

### Notes
- This repo is a field-ready template.
- Site-specific integration remains the responsibility of the deploying team.
