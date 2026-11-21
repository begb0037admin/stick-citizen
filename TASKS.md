# Stick Citizen personal setup

## Goal

Use the existing Stick Citizen app as Kevin's Star Citizen binding tool. Keep its full interface and features; do not rebuild the mapper. Get the left and right VKB Gladiator NXT sticks identified correctly, make it easy to assign Star Citizen actions, and validate a separate exported profile in game. Wingman knowledge and screenshot answers are a later phase, after the bindings are confirmed.

## Current state

- Upstream repository: https://github.com/ShoelessTim/stick-citizen
- Local checkout: `C:\Users\admin\github\stick-citizen`
- Working branch: `kevin/stickcitizen-personal-setup`
- Source baseline: `d0a0df3`
- Official Windows release v3.11.0 downloaded from GitHub Releases; SHA-256 verified against GitHub release metadata: `04fdce68074ff281c155960fa10735ea40c432ef9bac9ad90573a77e77fe6cd8`.
- Installer has not yet been run. Stick Citizen has not yet been launched.
- Native SDL detection sees three devices: VKBsim Gladiator NXT L, VPC Throttle MT-50CM2, and VKBsim Gladiator NXT R. Each VKB reports 6 axes, 128 buttons and 1 hat. SDL's order differs from the Windows Game Controllers list, so do not assign left/right by device order alone.
- The current Star Citizen live bindings file contains vJoy device labels. Do not use it as the new layout's starting point. Start clean and keep the current live profile untouched.
- User wants all of Stick Citizen's existing screens and functions: live input, control setup, action editing/search and modes, flight course, Fix It, layout scan, backups, helper and Star Citizen export.

## Task list

### In progress

- [ ] Install Stick Citizen v3.11.0 using the verified official installer.
- [ ] Launch it with the sticks connected and confirm it reports the left VKB, right VKB and throttle as separate devices.

### Next: live hardware verification

- [ ] Verify the left stick highlights only the left picture; verify the right stick highlights only the right picture.
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
