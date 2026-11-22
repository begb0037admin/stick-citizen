# Wingman Computer handover

22 November 2026. Wingman Core 3.2.14 reported ready. The existing Computer in the Star Citizen channel has the local StickCitizenLookup skill enabled with auto-activation.

## Current setup

- Computer gives the control instruction in chat and through its voice, waits for playback, then sends the labelled photos with the relevant controls circled.
- The skill reads Star Citizen LIVE's saved joystick overrides. It also supplies the six verified 4.10 defaults that match the export and are omitted by the override file. The full audit matched 140 assignments plus four separate VKB firmware lookups and rendered 31 distinct highlights.
- Device order for the audited profile is right VKB in slot 1, VPC throttle in slot 2 and left VKB in slot 3. Left B1 sends F. Right B1 sends mouse left-click. Left Y on foot uses the enabled forward/backward inversion.

## Files and rollback

| Item | Location |
| --- | --- |
| Local skill source | `C:/Users/admin/github/stick-citizen/integrations/wingman/stick_citizen_lookup` |
| Installed skill | `%APPDATA%/ShipBit/WingmanAI/custom_skills/stick_citizen_lookup` |
| Computer configuration | `%APPDATA%/ShipBit/WingmanAI/3_2_14/configs/Star Citizen/Computer.yaml` |
| Runtime log | `%APPDATA%/ShipBit/WingmanAI/3_2_14/logs/wingman-core.2026-11-22_14-16-28.log` |
| Before-pictures configuration backup | `%TEMP%/wingman-before-control-pictures-djbj0z70/Computer.yaml` |

The installed skill files matched the local source by SHA-256 at handover. The source and game profile are local files. The GitHub checkpoint contains the handover, tasks and test evidence.

To suspend the feature, disable **Stick Citizen Control Pictures** under Computer's Skills and reload the Star Citizen channel. To roll back the accompanying prompt change, restore the prior prompt from the backup and preserve any later changes to Computer's other settings.

## Test log

| Check | Observed result |
| --- | --- |
| Right B1 | Native Wingman chat displayed the right stick photo with B1 circled. A later typed test confirmed the left-click instruction preceded the image. |
| Enter salvage mode | A plain typed control question automatically returned left A4 up. A later test confirmed the instruction preceded the picture. |
| Fracture, 22:49 local | Computer posted the instruction for right A4 up and right Base F1. Core logged instruction playback finishing before both pictures were sent. Wingman's existing filler line can still appear during a lookup. |
| Walking forward | The full-size left stick instruction arrived before its picture. |
| Focused salvage fire, flight pitch, ground steering | Live typed questions emitted the matching pictures for right main trigger stage 1, right full-size forward/back and right full-size left/right. |
| Landing gear, 22:52 local | Computer posted “Use Left Hat A3 down” at 22:52:09 and sent the matching picture at 22:52:12. |

## Resume here

Ask Computer by voice which joystick control toggles landing gear. Confirm the instruction is audible and finishes before the picture appears. The previous microphone issue means voice input still needs a physical test. Then test actual right-stick look, flight, salvage and ground driving in Star Citizen. After any profile or firmware change, repeat the binding comparison and verify the affected picture.
