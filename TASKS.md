# Stick Citizen personal setup

## Goal

Use the existing Stick Citizen app as Kevin's Star Citizen binding tool. Keep its full interface and features; do not rebuild the mapper. Get the left and right VKB Gladiator NXT sticks identified correctly, make it easy to assign Star Citizen actions, and validate a separate exported profile in game. Also set up both mini-sticks to move the in-game cursor and send Enter when either is pressed, so menus can be used without reaching for the mouse or keyboard. Wingman knowledge and screenshot answers are a later phase, after the bindings are confirmed.

## Current state

- Upstream repository: https://github.com/ShoelessTim/stick-citizen
- Personal fork: https://github.com/begb0037admin/stick-citizen
- Local checkout: `C:\Users\admin\github\stick-citizen`
- Working branch: `kevin/stickcitizen-personal-setup`
- Source baseline: `d0a0df3`
- Official Windows release v3.11.0 downloaded from GitHub Releases; SHA-256 verified against GitHub release metadata: `04fdce68074ff281c155960fa10735ea40c432ef9bac9ad90573a77e77fe6cd8`.
- Installed at `C:\Users\admin\AppData\Local\Programs\Stick Citizen\StickCitizen.exe`; version 3.11.0. App launched and its window is open.
- Blank profile preserved at `profiles/kevin-clean-start.xml`. The current starter map is `profiles/kevin-flight-base.xml` and the app loads it. The left full-size stick Y axis maps `js3_y` to `spaceship_movement / v_strafe_longitudinal` with inversion, so pushing forward commands forward thrust. A copy is in Star Citizen's `controls/mappings` folder as `KevinVKBFlightBase.xml`; the live `actionmaps.xml` remains untouched. The in-game forward/reverse thrust check is still pending.
- Kevin wants both A1 mini-sticks to move the cursor and their centre presses to send Enter. The current step is the left A1 pointer only. The left A1 produced joystick hat events in a live capture, but the capture did not establish pointer movement from A1. Kevin reports neither mini-stick moves the pointer. The mode stored on the left stick has yet to be read.
- Read-only live SDL enumeration confirms three distinct devices: VKBsim Gladiator NXT L (GUID `0300e0251d2300000102000000000000`), VPC Throttle MT-50CM2 (GUID `030065c1443300009681000000000000`), and VKBsim Gladiator NXT R (GUID `030080231d2300000002000000000000`). Each VKB reports 6 axes, 128 buttons and 1 hat. SDL order is left, throttle, right; the prior Windows Game Controllers list showed right, throttle, left. Kevin confirmed that live movement and button input show on the correct stick picture.
- The current Star Citizen live bindings file contains vJoy device labels. Do not use it as the new layout's starting point. Start clean and keep the current live profile untouched.
- User wants all of Stick Citizen's existing screens and functions: live input, control setup, action editing/search and modes, flight course, Fix It, layout scan, backups, helper and Star Citizen export.

## Task list

### Done

- [x] Install Stick Citizen v3.11.0 using the verified official installer.
- [x] Create a blank, separate layout and configure the app to use it instead of Star Citizen's vJoy-based live profile.
- [x] Launch Stick Citizen 3.11.0. The window is open for hands-on verification.
- [x] Confirm live SDL detection reports the left VKB, VPC throttle and right VKB as separate named devices, and that the app's config uses exact-name slot overrides.

### Done: live hardware verification

- [x] Kevin verified the left stick highlights the left picture and the right stick highlights the right picture.
- [x] Kevin moved both sticks and confirmed live axis feedback works.
- [x] Kevin pressed controls and confirmed button feedback works.

### Flight starter: in-game check parked

- [x] Create a separate starter XML from Stick Citizen's built-in dual-stick layout, placing actions only on controls with known inputs.
- [x] Keep both A1 mini-sticks free of joystick actions so they can be configured as mouse/Enter controls.
- [x] Preserve the original blank XML and load the starter profile in Stick Citizen.
- [x] Kevin: confirm the app header shows `kevin-flight-base.xml · 60 bindings` and that Flight actions appear on the stick pictures.
- [x] Kevin: move the left stick forward and confirm it shows longitudinal strafe; press the right main trigger and confirm it shows the mapped fire action.
- [ ] In Star Citizen, select `KevinVKBFlightBase` from Control Profiles and verify left-stick forward gives forward thrust and pulling back slows/reverses.

### Current step: left A1 pointer

- [x] Capture joystick hat events from the left A1.
- [x] Download and unpack the official portable VKBDevCfg 0.93.89 utility.
- [ ] Check Windows computer control in a fresh Codex session. The connection still failed in the existing session after reopening the desktop app.
- [ ] Inspect the left A1 configuration in VKBDevCfg and record its joystick and virtual mouse settings.
- [ ] Present the specific change for approval if needed, back up the left VKB configuration before writing, and verify that left A1 movement alone moves the Windows pointer.

### Later steps (resume one at a time with Kevin's approval)

- [ ] Add and verify Salvage actions that are missing from the starter.
- [ ] Add and verify On foot actions.
- [ ] Add and verify Ground vehicle actions.
- [ ] Set up and verify right A1 pointer movement after the left pointer test passes.
- [ ] Set up and verify each A1 centre press sends Enter. Test each side in Windows, then verify the pointer and Enter in Star Citizen UI.

### Final Star Citizen validation

- [ ] Start from a blank layout, not the existing vJoy profile.
- [ ] Assign the desired flight and salvage actions using Stick Citizen's searchable action list.
- [ ] Use Fix It and Scan to catch wrong-device, missing-input, duplicate or category problems.
- [ ] Export as a separate Star Citizen profile; do not overwrite the live bindings file.
- [ ] Import that profile in game and verify representative flight and salvage actions.

### Later: Wingman reference

- [ ] After the profile is validated, give Wingman an up-to-date structured copy of every action, game mode, stick side, physical control label and input.
- [ ] When asked in game, Wingman should answer with the exact stick/control and show a relevant image with that control highlighted.
- [ ] Refresh Wingman's reference whenever the Stick Citizen profile changes.

## Guardrails

- Keep the upstream MIT copyright and license notices.
- Do not add Joystick Gremlin, vJoy or HIDHide for this direct-stick setup.
- Never replace Star Citizen's live bindings during setup; export and test a separate profile.
- Update this file as each task is completed and record the exact next action before stopping.

## Exact next action

In a new Windows Codex session, check desktop computer control before opening the staged VKBDevCfg. If connected, read the left A1 configuration and report it. See the [cold start brief](docs/KEVIN-COLD-START.md) for the utility path, evidence and approval boundary.
