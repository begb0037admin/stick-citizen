# Kevin's Stick Citizen setup — cold start brief

Checkpoint: 22 November 2026. Windows checkout: `C:\Users\admin\github\stick-citizen`. Fork branch: [`kevin/stickcitizen-personal-setup`](https://github.com/begb0037admin/stick-citizen/tree/kevin/stickcitizen-personal-setup). [Task list](../TASKS.md).

## Start here

**Current task: make the left A1 mini-stick move the Windows pointer.** The mouse-only configuration has been written to the left VKB and read back successfully. Exact next action: Kevin should test pointer movement by moving only the left A1 while leaving the physical mouse still, then report whether the pointer responds and stops on release. Handle software operation yourself; do not move the physical stick for Kevin.

1. Test the left A1 on the Windows desktop with Kevin moving only the stick while leaving the physical mouse still. Pass when the pointer responds to the requested directions and stops on release. The existing A1 press-to-toggle assignment remains in place; if the pointer does not respond, have Kevin press the A1 once and test again.
2. If the live test fails, inspect the left profile’s Mouse speed/dead zone and A1 mode state before adjusting anything. Do not modify the right stick yet.
3. After the left pointer passes and Kevin approves the next step, continue with the right A1 pointer movement and Enter on both A1 presses.

## Verified and pending

- **Left A1 VKB mouse setup, 22 November 2026:** The original selected `VKBsim Gladiator NXT L XT v2.090` profile was backed up before writing at `%LOCALAPPDATA%\StickCitizen\tools\VKBDevCfg-0.93.89\VKBsim Gladiator NXT L   profile 1.cfg` (2048 bytes). After Kevin approved the mouse-only setup, `VKBDevCfg-C` v0.93.89 wrote the left device and a fresh Get returned `Read data - OK`. Stored Global > Common: Mouse = Relative; Active = Always On; Speed = 0; Curve = OFF; FL unchecked. Stored Profile > POVs: POV #1 = Common; Output = Mouse Rel; VC #1; 2D enabled; X=5, Y=6; dead zone now reads 18; Cross; Active On/Off. The prior read showed POV output = POV and dead zone 50; the value 18 appeared after the write/readback and was left unchanged. Profile > Axis shows physical axes 5/6 as Rot X/Rot Y and analog. Physical layer Reg #2 Line 5 remains `uSSw` / `But.Alt • POV1`; Reg #3 Lines 1–4 had supplied the former digital POV directions. No live pointer test has been performed yet. Exact next action: Kevin moves only left A1 with the physical mouse still, reports pointer response and whether it stops on release; if there is no response, press A1 once and retry.
- The left VKB is present in Windows. A previous live capture saw its A1 send POV hat directions. Pointer changes during that capture could not be attributed to A1, and Kevin reports neither mini-stick moves the pointer. The current left configuration is now set to Mouse Rel and awaits a live pointer test.
- Stick Citizen 3.11.0 is installed. Both VKBs were identified by distinct names and Kevin confirmed that the correct stick picture lights up. Browser, Windows and SDL device order are not interchangeable with Star Citizen joystick slots.
- The separate flight starter `profiles/kevin-flight-base.xml` is staged for export/import as `KevinVKBFlightBase.xml`. The in-game forward/reverse thrust check is still open and parked while the left A1 is being handled.
- After the left pointer passes and Kevin approves the next step, finish right A1 pointer movement and Enter on both A1 presses. The broader project uses the existing Stick Citizen UI and covers flight, salvage, on foot and ground vehicles. Wingman comes after the game bindings are verified and should answer from the verified profile and show the physical control on a picture.

To resume, open the Stick Citizen workspace in a new Windows Codex chat and say: **Read `docs/KEVIN-COLD-START.md` and resume the left A1 pointer setup. Start by checking desktop computer control.**
