# Reporting a problem

A clear report gets a problem fixed sooner. This page shows what to include.

## Before you report

- Check [Troubleshooting](troubleshooting.md) for common causes.
- Make sure you run the newest PlayNice release listed on the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases).

## Find your PlayNice version

The issue forms ask for **PlayNice version** and **Windows version**. Both are required, because a problem often depends on the exact build.

**If PlayNice opens:** open the **...** menu and choose **About PlayNice**. The version is on the second line (for example `0.1.0-beta.1`). **Copy details** puts it on the clipboard.

**If PlayNice will not open**, use one of these instead:

- The installer's file name: `PlayNice-<version>-Setup-x64.exe`.
- **Settings > Apps > Installed apps**: find **PlayNice** and read its version.
- In File Explorer, right-click `playnice.exe` in the PlayNice install folder, choose **Properties**, then **Details**, and read **Product version**.

If you cannot find it, write "cannot open PlayNice" and say which installer you used. The report is still welcome.

## Find your Windows version

Press the Windows key, type `winver` and press Enter. Copy the version and build shown (for example "Windows 11, version 25H2 (build 26200)").

## Export a diagnostic report

1. In PlayNice, open **Settings**.
2. Under **Advanced**, next to **Diagnostics**, choose **Export diagnostic report…**.
3. Read the summary. Choose **Review report** to see the exact contents.
4. Choose **Save…** and pick a folder.

PlayNice saves a ZIP file on your computer. It does not upload anything. See [Diagnostic report](diagnostic-report.md) for what it contains and what it does not.

You do not need a diagnostic report to open an issue. It helps most for sound and startup problems.

## Open an issue

1. Go to the **Issues** tab of this repository and choose **New issue**.
2. Pick **Bug report**, **Audio issue** or **Feature request**.
3. Fill in the form. To attach a diagnostic report, drag the ZIP file into the box.

Anything you attach to a public issue may be accessible to anyone, and a diagnostic report contains system information. Read the ZIP before you attach it, and do not attach it if you are not comfortable sharing it. Attaching it is always optional.

## Describing a sound problem

Say what you heard and what you expected, and describe the devices by kind (a Bluetooth speaker, a monitor over HDMI, a USB headset). Useful details:

- What was playing, and where (a web browser, a media player).
- Whether that program's **Output** in the Windows Volume mixer was set to **CABLE Input**.
- How many speakers were active in the setup.
- Whether it began after the computer slept or a speaker reconnected.
- Whether it happens every time or only sometimes.

## Startup and installer problems

Say which installer you used, whether you installed for yourself or for all users, and what Windows showed. If Windows blocked or warned about the installer, quote the message exactly. Do not turn off Defender or SmartScreen to work around it; the options for Smart App Control are in the [installation guide](installation.md#if-smart-app-control-blocks-playnice).

For a sign-in problem, also say whether **Start PlayNice at sign-in** was on, whether the tray icon appeared, and whether `playnice.exe` and `playnice-control.exe` were running (Task Manager, **Details** tab).

## A sleep or wake problem

Note how long the computer slept, whether the speakers were switched on when it woke, and what you saw (no sound, a message, nothing). Then export a diagnostic report right after the problem, before restarting PlayNice if you can.

## If PlayNice will not start

Restart the computer and try once more. If it still does not open, note any message Windows shows and open an issue with:

- your Windows version,
- how you installed PlayNice (for me only or for all users), and
- the PlayNice version, found as described above.

The diagnostic report is made from the PlayNice window, so it is not available in this case.

## What not to post

Do not post passwords, account details, complete registry exports, memory dumps or device serial numbers. Do not post the raw files from **Open folder** in Settings. If a developer needs more detail, you will be asked separately.

To report a security problem, do not open a public issue; use the private reporting described in the [security policy](../SECURITY.md).
