# Stick Citizen personal setup

## Goal

Use the existing Stick Citizen app as Kevin's Star Citizen binding tool. Keep its full interface and features; do not rebuild the mapper. Get the left and right VKB Gladiator NXT sticks identified correctly, make it easy to assign Star Citizen actions, and validate a separate exported profile in game. Also set up one mini-stick to move the in-game cursor and send Enter when pressed, so menus can be used without reaching for the mouse or keyboard. Wingman knowledge and screenshot answers are a later phase, after the bindings are confirmed.

## Current state

- Upstream repository: https://github.com/ShoelessTim/stick-citizen
- Personal fork: https://github.com/begb0037admin/stick-citizen
- Local checkout: `C:\Users\admin\github\stick-citizen`
- Working branch: `kevin/stickcitizen-personal-setup`
- Source baseline: `d0a0df3`
- Official Windows release v3.11.0 downloaded from GitHub Releases; SHA-256 verified against GitHub release metadata: `04fdce68074ff281c155960fa10735ea40c432ef9bac9ad90573a77e77fe6cd8`.
- Installed at `C:\Users\admin\AppData\Local\Programs\Stick Citizen\StickCitizen.exe`; version 3.11.0. App launched and its window is open.
- Clean profile at `profiles/kevin-clean-start.xml`; it has no action bindings. The installed app config points to it and maps Star Citizen slots by exact device names: js1 right VKB, js2 VPC throttle, js3 left VKB. Stick-side live feedback has been physically confirmed; the Star Citizen XML slot order still needs in-game validation before import.
- Kevin wants the right-hand A1 mini-stick to move the cursor and its center press to send Enter. This is VKB firmware output (virtual mouse + keyboard), separate from Stick Citizen's joystick XML bindings. Back up the current VKB profiles before any firmware write and confirm the center press can send Enter while cursor mode is active.
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

### In progress: prepare a usable starting layout

- [ ] Inspect and back up both VKB firmware profiles before changing the right A1 mini-stick.
- [ ] Configure the right A1 mini-stick for virtual mouse movement and center press for Enter, if supported together by its current firmware profile; leave the left stick unchanged at first.
- [ ] Test cursor movement and Enter in a harmless Windows text field, then in one Star Citizen UI.
- [ ] Skip Stick Citizen's analog-axis mini-stick wizard step if A1 is not being used for flight axes; mouse mode sends mouse events, not joystick axes.
- [ ] Choose Stick Citizen's built-in Sublight starting layout or keep the blank layout; inspect the assignments on the stick pictures before changing anything.

### Next: personal Star Citizen layout

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

Next, inspect and back up the current VKB firmware profile, then configure and test the right A1 mini-stick as cursor movement with its press sending Enter. This is configured in VKB firmware, not in Stick Citizen's XML. Once it works, choose the built-in **Sublight** layout as a visible starter, review assignments on both stick pictures, and use **Fly** before exporting anything to Star Citizen.
