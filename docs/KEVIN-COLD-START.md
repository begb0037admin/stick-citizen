# Kevin's Stick Citizen setup — cold start brief

Checkpoint: 22 November 2026. Windows checkout: `C:\Users\admin\github\stick-citizen`. Fork branch: [`kevin/stickcitizen-personal-setup`](https://github.com/begb0037admin/stick-citizen/tree/kevin/stickcitizen-personal-setup). [Task list](../TASKS.md).

## Start here

**Current task: make the left A1 mini-stick move the Windows pointer.** The last approved device action was a read-only check of the left A1 settings. Work one step at a time. State the action before proceeding and ask before moving to a new step or applying a configuration change. Handle software operation yourself. Kevin can move the physical stick when a live test is ready.

1. In the fresh Windows Codex session, check desktop computer control. In the prior session, both checks returned `Computer Use native pipe is unavailable` (Windows error 2) even after reopening the desktop app. The reopened app started a fresh helper while the existing conversation still showed an older tool host. A new session has yet to be tried. If the error persists, investigate the connection or a documented read-only route. A controller input check alone cannot read the stored VKB configuration.
2. When desktop control works, open the staged portable VKB utility under `%LOCALAPPDATA%\StickCitizen\tools\VKBDevCfg-0.93.89\VKBDevCfg-C.exe`. It was downloaded and unpacked from [VKB's official downloads page](https://vkbsimcontrollers.com/pages/downloads). Select `VKBsim Gladiator NXT L` by exact name and inspect its A1 mode switch and virtual mouse settings. Record what is actually configured. The current device approval covers inspection only.
3. If a change is needed, show Kevin the proposed left A1 change and get approval. Back up the current left VKB profile before writing. Test on the Windows desktop with Kevin moving only the left A1 while leaving the physical mouse still. Pass when the pointer responds to the requested directions and stops on release. Report the result before starting the next step.

## Verified and pending

- The left VKB is present in Windows. A previous live capture saw its A1 send POV hat directions. Pointer changes during that capture could not be attributed to A1, and Kevin reports neither mini-stick moves the pointer. The current VKB configuration was not read or changed.
- Stick Citizen 3.11.0 is installed. Both VKBs were identified by distinct names and Kevin confirmed that the correct stick picture lights up. Browser, Windows and SDL device order are not interchangeable with Star Citizen joystick slots.
- The separate flight starter `profiles/kevin-flight-base.xml` is staged for export/import as `KevinVKBFlightBase.xml`. The in-game forward/reverse thrust check is still open and parked while the left A1 is being handled.
- After the left pointer passes and Kevin approves the next step, finish right A1 pointer movement and Enter on both A1 presses. The broader project uses the existing Stick Citizen UI and covers flight, salvage, on foot and ground vehicles. Wingman comes after the game bindings are verified and should answer from the verified profile and show the physical control on a picture.

To resume, open the Stick Citizen workspace in a new Windows Codex chat and say: **Read `docs/KEVIN-COLD-START.md` and resume the left A1 pointer setup. Start by checking desktop computer control.**
