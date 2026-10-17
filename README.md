# TheoryBoard THY333: original firmware and update utility (archive)

The TheoryBoard THY333's original firmware update and the manufacturer's update utility,
kept available for owners now that the manufacturer (Irijule, Inc.) and its download site
no longer exist. Use them to put the original firmware back on a board, for example after
trying [TBOSS](https://github.com/armandhammer/TBOSS), the open-source firmware.

**Download:** [Releases → v5](../../releases/tag/v5)

> These files are the manufacturer's original software, unmodified. They are **not**
> open source and **not** covered by TBOSS's license. They are shared here with the
> permission of the TheoryBoard's original developer so that existing boards can keep
> being restored.

## Files

| File | What it is | SHA-256 |
| --- | --- | --- |
| `THY333_v5.333` | Firmware update file, version 5 (133,630 bytes) | `125e18005b4e6f797d2b300649f5207d3e7a6f4b2e0af5e3000234b4f4efe990` |
| `THY333UpdateUtilityInstaller.zip` | Windows: *THY333 Update Utility Setup* 1.1 (Irijule, Inc.; the installer is not code-signed) | `b87f0de57e8addcf139054a636ea462f1298210f3ffd413cbdc4041afd4eec8a` |
| `TheoryBoard_FW_W_MacInstall.zip` | macOS: *THY333 Update Utility* app (Intel; macOS 10.12 or newer) and the same `THY333_v5.333` | `c985eade96c045a667b378521fce170c09abd5c7ea7eb30c63826f485f4c4eaf` |

The archives are exactly as they were distributed, including their folder names.

## Putting the original firmware back

1. Optional: if the board runs TBOSS, back up its external memory chip first with the
   [TBOSS web editor](https://armandhammer.github.io/TBOSS/) (*Back up external memory*).
   The chip holds the original firmware's own data, and the update may re-initialise it.
2. Install and open the update utility (Windows: run the installer from the zip; macOS:
   unzip the app, then right-click → *Open* the first time, since it is not notarised).
3. Start the board in **update mode**: unplug USB, hold the **top-left and bottom-left
   pads of the left (chord) half**, plug USB back in and keep holding for about 3 seconds.
   The screen shows the TheoryBoard logo and the five buttons below it stay lit.
4. In the utility, choose `THY333_v5.333` and start the update.
5. The utility may stay on **"Updating firmware... finalizing"** while the board shows
   "Firmware update, do not unplug device". On the board this was confirmed on, the update
   had already finished and the board was only waiting for the utility. After about
   **5 minutes** on that message, close the utility, unplug the board and plug it in
   normally: the original firmware starts.
6. If it does not start, enter update mode again and repeat. The board's start-up loader,
   which provides update mode, is not changed by updates.

To go back to TBOSS, use its [browser installer](https://armandhammer.github.io/TBOSS/install.html).

## Checking a download

Windows (PowerShell): `Get-FileHash .\THY333_v5.333` · macOS/Linux: `shasum -a 256 THY333_v5.333`.
The result must match the table above.
