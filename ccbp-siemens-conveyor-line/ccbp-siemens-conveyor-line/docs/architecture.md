## Architecture Notes

This repo is intentionally **spec-first**:

1. `spec/` defines the authoritative intent (CCBP control spec).
2. `plc/` contains implementation artifacts (SCL, OB1 skeleton, DB plan).
3. `hmi/` contains a binding contract for WinCC.

### Key Governance Invariants
- Safety dominance (`xEStopOK` gates all motion outputs).
- Bounded reset (no auto-reset; reset only when safe).
- Deterministic precedence (ordering is explicit in spec and banner logic).

### HMI Policy: NO_INST_DB
WinCC binds only to:
- `DB_CL01_LineStat`
- `DB_CL01_S01_Stat`..`DB_CL01_S05_Stat`
and to physical I/O tags as mirrored into these status DBs.

FB instance DBs exist for PLC execution but are not read by HMI.
