# Stick Citizen personal setup

## Goal

Use the existing Stick Citizen app as Kevin's Star Citizen binding tool. Keep its full interface and features; do not rebuild the mapper. Get the left and right VKB Gladiator NXT sticks identified correctly, make it easy to assign Star Citizen actions, and validate a separate exported profile in game. Wingman knowledge and screenshot answers are a later phase, after the bindings are confirmed.

## Current state

- Upstream repository: https://github.com/ShoelessTim/stick-citizen
- Personal fork: https://github.com/begb0037admin/stick-citizen
- Local checkout: `C:\Users\admin\github\stick-citizen`
- Working branch: `kevin/stickcitizen-personal-setup`
- Source baseline: `d0a0df3`
- Official Windows release v3.11.0 downloaded from GitHub Releases; SHA-256 verified against GitHub release metadata: `04fdce68074ff281c155960fa10735ea40c432ef9bac9ad90573a77e77fe6cd8`.
- Installed at `C:\Users\admin\AppData\Local\Programs\Stick Citizen\StickCitizen.exe`; version 3.11.0. App launched and its window is open.
- Clean profile at `profiles/kevin-clean-start.xml`; it has no action bindings. The installed app config points to it and maps Star Citizen slots by exact device names: js1 right VKB, js2 VPC throttle, js3 left VKB. Treat that left/right assignment as provisional until physically confirmed.
- Read-only live SDL enumeration confirms three distinct devices: VKBsim Gladiator NXT L (GUID `0300e0251d2300000102000000000000`), VPC Throttle MT-50CM2 (GUID `030065c1443300009681000000000000`), and VKBsim Gladiator NXT R (GUID `030080231d2300000002000000000000`). Each VKB reports 6 axes, 128 buttons and 1 hat. SDL order is left, throttle, right; the prior Windows Game Controllers list showed right, throttle, left. The app config uses exact names, but physical picture/input confirmation is still required.
- The current Star Citizen live bindings file contains vJoy device labels. Do not use it as the new layout's starting point. Start clean and keep the current live profile untouched.
- User wants all of Stick Citizen's existing screens and functions: live input, control setup, action editing/search and modes, flight course, Fix It, layout scan, backups, helper and Star Citizen export.

## Task list

### Done

- [x] Install Stick Citizen v3.11.0 using the verified official installer.
- [x] Create a blank, separate layout and configure the app to use it instead of Star Citizen's vJoy-based live profile.
- [x] Launch Stick Citizen 3.11.0. The window is open for hands-on verification.
- [x] Confirm live SDL detection reports the left VKB, VPC throttle and right VKB as separate named devices, and that the app's config uses exact-name slot overrides.

### In progress: live hardware verification

- [ ] Kevin: verify the left stick highlights only the left picture; verify the right stick highlights only the right picture.
- [ ] Move each stick forward/back and left/right; confirm the correct axes and direction are shown.
- [ ] Press one clearly identifiable button on each stick; confirm the correct physical control lights up.
- [ ] Run the setup wizard for any controls whose NXT mapping is uncertain; do not assume the NXT EVO preset matches without checking.

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

With Stick Citizen open, move the **left** stick forward and confirm the live indicator and highlighted image are on the left. Then move the **right** stick forward and confirm they are on the right. If either side is reversed, stop there and correct device assignment before mapping controls.
