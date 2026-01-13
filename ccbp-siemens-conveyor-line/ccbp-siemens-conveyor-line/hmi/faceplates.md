# WinCC Faceplates — Binding Contract (NO_INST_DB)

## FP_LineOverview
Bind only to:
- `DB_CL01_LineStat.*` for mode/permissives/banner
- `DB_CL01_S0X_Stat.*` for each zone tile

## FP_ConveyorSection (apply to each zone)
Commands:
- `Cmd.StartLine` -> `DB_CL01_HMI.xStartLine`
- `Cmd.StopLine`  -> `DB_CL01_HMI.xStopLine`
- `Cmd.ResetLine` -> `DB_CL01_HMI.xResetLine`
- `Cmd.ManReq`    -> `DB_CL01_HMI.xManReq_S0X`
- `Cmd.Inhibit`   -> `DB_CL01_HMI.xInhibit_S0X`

Status:
- `Stat.CmdRun`   -> `DB_CL01_S0X_Stat.xCmdRun`
- `Stat.Faulted`  -> `DB_CL01_S0X_Stat.xFaulted`
- `Stat.FaultCode`-> `DB_CL01_S0X_Stat.diFaultCode`
- `Stat.JamOK`    -> `DB_CL01_S0X_Stat.xJamOK`
- `Stat.FbRunning`-> `DB_CL01_S0X_Stat.xFbRunning`
- `Sens.EntryPE`  -> `DB_CL01_S0X_Stat.xPE_Entry`
- `Sens.ExitPE`   -> `DB_CL01_S0X_Stat.xPE_Exit`

Alarms:
- `Alm[1..8].Active`   -> `DB_CL01_S0X_Stat.aAlm[i].xActive`
- `Alm[1..8].Code`     -> `DB_CL01_S0X_Stat.aAlm[i].diCode`
- `Alm[1..8].Priority` -> `DB_CL01_S0X_Stat.aAlm[i].iPriority`
