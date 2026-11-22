# Stick Citizen personal setup

## Goal

Use Stick Citizen to build and save a separate Star Citizen profile for dual VKB sticks. Cover flight, salvage, on-foot movement and ground vehicles. Use joystick controls for gameplay and use the VKB A1 pointer plus B1 mouse clicks for cursor/menu use. Verify the exported profile in Star Citizen before starting the later Wingman reference phase.

## Current state

- Upstream repository: https://github.com/ShoelessTim/stick-citizen
- Personal fork: https://github.com/begb0037admin/stick-citizen
- Local checkout: `C:\Users\admin\github\stick-citizen`
- Working branch: `kevin/stickcitizen-personal-setup`
- Stick Citizen 3.11.0 is installed and open.
- Current editable layout: `profiles/kevin-vkb-joystick.xml` (140 bindings). Separate Star Citizen export: `C:\Program Files\Roberts Space Industries\StarCitizen\LIVE\user\client\0\controls\mappings\layout_KevinVKBJoystick_exported.xml`.
- Comparison inventory: `docs/STAR-CITIZEN-JOYSTICK-BINDINGS.csv`. It contains 840 unique rows: 743 actions in Stick Citizen's 4.7 picker, 838 joystick-capable actions in installed Star Citizen 4.10, 741 shared actions and 97 game actions missing from the picker. Of the 97, 93 are special emote/view/spectator/stopwatch/server-renderer actions; four are gameplay actions in `seat_general` or `spaceship_docking`.
- All 140 chosen profile actions appear in both the picker and Star Citizen. The rest of the inventory is not assigned. Profile map counts: 30 salvage, 25 player/on foot, 19 ground vehicle and 66 ship/shared actions.
- Star Citizen's last `Game.log` identified JS1 as right VKB, JS2 as VPC throttle and JS3 as left VKB. The throttle is not mapped in this profile.
- On foot: left full-size stick X/Y moves/strafe, right X/Y looks. Kevin reported left Y was reversed, so `fps_move_longitudinal invert="1"` is now present in the editable profile and Star Citizen export for JS3. The installed game defines this option for the `gp_movey` binding. The previous `gp_movey` option tag was incorrect. Reselect the profile and test direction and spring-centre stop.
- Ground: left stick drives, right stick steers, with brake and boost controls assigned.
- Salvage: left A4 up changes into salvage mode; right main trigger focuses/fires the active beam. Remaining beam and tractor actions are assigned.
- VKB firmware: left B1 is keyboard F (logical slot 16, confirmed after Set). Right B1 is mouse left-click (logical slot 16, confirmed after Set and reconnect). Kevin previously confirmed left A1 pointer movement on Windows. Physical B1 keypress verification is pending.
- Stick Citizen's whole-layout scan passed on 140 binds across 3 sticks: no problems found, with 11 controls having no action (spare controls). Its report says JS1 was guessed from plug-in order, so per-stick slot verification is still pending. The export has not been tested in game. The live `actionmaps.xml` remains untouched.
- The full action inventory and checkpoint are in [`docs/KEVIN-COLD-START.md`](docs/KEVIN-COLD-START.md).

## Task list

### Complete

- [x] Install the verified official Stick Citizen 3.11.0 release and confirm separate named input devices for both VKBs and the VPC throttle.
- [x] Set up both VKB A1 mini-sticks as mouse pointers in VKB firmware, with left B1/right B1 as mouse left/right clicks. Kevin confirmed the clicks work on Windows.
- [x] Compare the app's available actions with the installed Star Citizen joystick action inventory and save the full comparison CSV.
- [x] Build the 140-binding `KevinVKBJoystick` profile for flight, salvage, on-foot and ground controls.
- [x] Load the profile in Stick Citizen and use Save for Star Citizen to create the separate LIVE Control Profiles export.
- [x] Read back the Star Citizen export and confirm its 140 assignments match the loaded app profile.

### In-game validation — next

- [ ] Reselect `KevinVKBJoystick` from Star Citizen LIVE Options > Keybindings > Control Profiles to reload the updated left-Y on-foot inversion.
- [ ] In Stick Citizen Fix It, press one mapped button on each VKB and confirm the detected JS slots match the export.
- [ ] Verify left stick forward and release-to-centre stop, left/right strafe and right stick look on foot.
- [ ] Verify flight direction on left Y and pitch/yaw on right stick.
- [ ] Verify salvage mode, beam selection/fire/spacing and tractor controls.
- [ ] Verify ground driving, steering, brake and boost.
- [ ] Record any action that is missing or points in the wrong direction; then correct it in Stick Citizen and re-export the separate profile.
- [ ] Confirm the A1 cursor pointer behavior on both sticks in game. Check left B1 sends F and right B1 sends left-click.

### Later: Wingman reference

- [ ] After the in-game profile is verified, give Wingman the current actions, modes, stick side, control label and input mapping.
- [ ] Have Wingman identify the exact stick/control and show it on a relevant picture when asked in game.
- [ ] Refresh the reference whenever the verified Stick Citizen profile changes.

## Guardrails

- Keep the upstream MIT copyright and license notices.
- Do not add Joystick Gremlin, vJoy or HIDHide for this direct-stick setup.
- Never replace Star Citizen's live `actionmaps.xml` during setup; import and test the named profile separately.
- Update this file and `docs/KEVIN-COLD-START.md` with the factual checkpoint and exact next action before stopping.

On-foot left Y inversion is enabled in the active Star Citizen profile for the left VKB (Joystick/HOTAS 3). Kevin confirmed this step was done.

## Exact next action

Continue the remaining in-game checks with right-stick look, then flight, salvage and ground driving.
