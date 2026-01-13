# UDTs and FBs

This repo ships a complete OB1 skeleton and governance/spec artifacts.

The following block names are assumed to exist in your TIA project (from your Siemens field-ready library):
- UDTs: Udt_Alarm, Udt_ModeAuth
- FBs:  FB_ModeAuthority, FB_ConveyorSection, FB_AlarmRouter

If you want this repo to include the full SCL source for those blocks, add them under:
- plc/udt/
- plc/fb/
