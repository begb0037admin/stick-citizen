# Kevin's Stick Citizen setup — cold start brief

Checkpoint: 22 November 2026. Windows checkout: `C:\Users\admin\github\stick-citizen`. Fork branch: [`kevin/stickcitizen-personal-setup`](https://github.com/begb0037admin/stick-citizen/tree/kevin/stickcitizen-personal-setup). [Task list](../TASKS.md).

## Start here

**Current status:** The 140-binding `KevinVKBJoystick` export is the current profile. Star Citizen has saved the left-stick walking inversion. Wingman Computer uses the audited bindings and shows each picture after the instruction. See the [Wingman handover and test log](WINGMAN-HANDOVER.md) for live status, paths and rollback.

## Stick Citizen and Star Citizen action comparison

- The comparison file [`STAR-CITIZEN-JOYSTICK-BINDINGS.csv`](STAR-CITIZEN-JOYSTICK-BINDINGS.csv) inventories 840 unique action rows across the installed Star Citizen 4.10 joystick-capable actions and Stick Citizen's bundled 4.7 picker.
- The picker contains 743 actions. Star Citizen exposes 838 actions that support joystick bindings. 741 actions appear in both; 97 Star Citizen actions are not in this picker version. 93 of those belong to emote, spectator, view-director, stopwatch or server-renderer maps. Four are gameplay actions in `seat_general` or `spaceship_docking`.
- This export assigns 140 selected actions, all found in both the picker and the game. The CSV lists each input assigned by this profile and identifies picker coverage. The other game actions are inventory choices, not assigned controls.

## Current profile and mode coverage

- Editable Stick Citizen profile: [`profiles/kevin-vkb-joystick.xml`](../profiles/kevin-vkb-joystick.xml). Export saved to `C:\Program Files\Roberts Space Industries\StarCitizen\LIVE\user\client\0\controls\mappings\layout_KevinVKBJoystick_exported.xml`. The export was read back and its 140 input/action/activation/map assignments matched the loaded profile.
- 30 salvage actions cover salvage mode, beam focus, fire modes, spacing, nudges and tractor controls. Salvage mode is left A4 up; the right main trigger focuses/fires the active beam.
- 25 player/on-foot actions include movement, strafe, sprint, jump, crouch, weapon controls, interaction and item actions. Left full-size stick X/Y controls strafe/walk; the left Y uses the `fps_move_longitudinal` inversion setting after Kevin reported forward/backwards was reversed. The spring-centred axis returns to stop. Right X/Y controls look.
- 19 ground-vehicle actions cover driving, steering, braking, boost and other vehicle controls. The VPC throttle is not mapped in this profile.
- Flight and shared ship controls make up the rest. The profile maps left/right VKBs using the Star Citizen device order confirmed from `Game.log`: JS1 right VKB, JS2 VPC throttle, JS3 left VKB.
- VKB firmware: left B1 is keyboard F (logical slot 16, confirmed after Set). Right B1 is mouse left-click (logical slot 16, confirmed after Set and reconnect). Kevin previously confirmed left A1 pointer movement on Windows. Physical B1 keypress verification is pending.

## Verification and pending

- Stick Citizen's whole-layout scan passed: 140 binds on 3 sticks, no problems found, and 11 controls with no action (spare buttons are fine). The scan warns that its JS1 device assignment is guessed from plug-in order; a control press in Fix It is needed to confirm the physical stick/slot. The editable profile and LIVE export now contain the JS3 `fps_move_longitudinal invert="1"` option for left-stick on-foot movement. The installed game defines this option for the `gp_movey` binding. The previous `gp_movey` option tag was incorrect. Kevin confirmed the inversion setting in game. Release-to-stop remains on the physical checklist.
- Do not overwrite the live `actionmaps.xml`. Keep testing the named `KevinVKBJoystick` export as a separate profile.
- The separate older `profiles/kevin-flight-base.xml` is not the current all-mode profile.
- Wingman Computer looks up the 134 saved joystick overrides and six matching built-in assignments, plus the firmware controls. The 140-assignment export contains six additional assignments not present in the game's saved profile. The reference was verified in the native Computer configuration after launch. Wingman reported microphone input disabled. The local custom skill StickCitizenLookup is enabled for Computer. It reads the saved game bindings and uses Stick Citizen's original photos and coordinates to highlight the matching physical control. Source: `integrations/wingman/stick_citizen_lookup` in the local checkout. Installed copy: `%APPDATA%/ShipBit/WingmanAI/custom_skills/stick_citizen_lookup`. A live Computer text lookup displayed right B1 circled in native Wingman chat. After shortening the prompt to avoid truncation and enabling auto-activation, a plain salvage-mode control question also emitted a highlighted PNG automatically.

On-foot left Y inversion is enabled in the active Star Citizen profile for the left VKB (Joystick/HOTAS 3). Kevin confirmed this step was done.

Wingman fracture lookup now resolves both active spaceship_salvage bindings even when the request arrives with seat_general. The live typed request emitted two captioned pictures: right Hat A4 up to select fracture, and right Base F1 to toggle the fracture beam. In-game beam behavior and spoken lookup have not been checked.

The Wingman lookup audit compared the 140 exported bindings with the saved in-game overrides and the installed 4.10 defaults. Computer now includes six built-in bindings omitted from the saved overrides: flight pitch/yaw/roll, ground pitch/yaw and focused salvage fire. Exact binding coverage matched all 140 exported assignments and four firmware controls, with 31 distinct picture highlights rendered. Live text requests delivered the expected focused salvage fire, flight pitch and ground steering pictures. The skill reads saved overrides ahead of the built-in fallback.

Computer now posts and speaks its control instruction before emitting the highlighted pictures. A live typed fracture question posted the requested instruction, completed its speech playback and then sent the A4 and F1 pictures in that order. The same order was verified on live typed lookups for entering salvage mode, walking forward on foot, and right B1. Wingman's existing filler message can still appear during a tool call.

## Exact next action

Ask Computer by voice which joystick control toggles landing gear. Confirm the spoken instruction finishes before the picture appears. Continue the remaining in-game checks with right-stick look, flight, salvage and ground driving, then refresh Computer's reference after any binding changes.
