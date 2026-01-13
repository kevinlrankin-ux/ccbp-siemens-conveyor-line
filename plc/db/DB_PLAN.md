# DB Plan (HMI_POLICY: NO_INST_DB)

## Shared DBs
- `DB_CL01_Mode` — resolved mode/authority (`Udt_ModeAuth`)
- `DB_CL01_HMI` — operator inputs (Start/Stop/Reset, HOA, authority, inhibits, manual requests)
- `DB_CL01_Seq` — sequencing requests and readiness flags
- `DB_CL01_LineStat` — HMI-safe line view (mode + permissives + alarm banner)

## Per-Zone HMI-Safe Status DBs
- `DB_CL01_S01_Stat`..`DB_CL01_S05_Stat` — each contains:
  - `xCmdRun`, `xFaulted`, `diFaultCode`
  - mirrored inputs: `xJamOK`, `xFbRunning`, `xPE_Entry`, `xPE_Exit`
  - `xAutoReq`, `xManReq`
  - `aAlm[1..8] : Udt_Alarm`

## Per-Zone Instance DBs (Not for HMI)
- `DB_CL01_S01_Inst`..`DB_CL01_S05_Inst` — instance DBs for `FB_ConveyorSection`
