# Reporting a problem

A clear report gets a problem fixed sooner. This page shows what to include.

## Before you report

- Check [Troubleshooting](troubleshooting.md) for common causes.
- Make sure you run the latest PlayNice release.

## Find your PlayNice version

Open PlayNice, open the menu and choose **About PlayNice**. The version is on the second line. **Copy details** puts it on the clipboard.

## Export a diagnostic report

1. In PlayNice, open **Settings**.
2. Under **Advanced**, next to **Diagnostics**, choose **Export diagnostic report…**.
3. Read the summary. Choose **Review report** to see the exact contents.
4. Choose **Save…** and pick a folder.

PlayNice saves a ZIP file on your computer. It does not upload anything. See [Diagnostic report](diagnostic-report.md) for what it contains.

You do not need a diagnostic report to open an issue. It helps most for sound and startup problems.

## Open an issue

1. Go to the **Issues** tab of this repository and choose **New issue**.
2. Pick **Bug report**, **Audio issue** or **Feature request**.
3. Fill in the form. To attach a diagnostic report, drag the ZIP file into the box.

Anything you attach to a public issue may be accessible to anyone, and a diagnostic report contains system information. Read the ZIP before you attach it, and do not attach it if you are not comfortable sharing it. Attaching it is always optional.

## Describing a sound problem

Say what you heard and what you expected, and describe the devices by kind (a Bluetooth speaker, a monitor over HDMI, a USB headset). Useful details:

- What was playing, and where (a web browser, a media player).
- How many speakers were active in the setup.
- Whether it began after the computer slept or a speaker reconnected.
- Whether it happens every time or only sometimes.

## Startup and installer problems

Say which installer you used, whether you installed for yourself or for all users, and what Windows showed. If Windows blocked or warned about the installer, quote the message exactly. Do not turn off Windows security features to work around it.

## A sleep or wake problem

Note how long the computer slept, whether the speakers were switched on when it woke, and what you saw (no sound, a message, nothing). Then export a diagnostic report right after the problem, before restarting PlayNice if you can.

## If PlayNice will not start

Restart the computer and try once more. If it still does not open, note any message Windows shows and open an issue with your Windows version and how you installed PlayNice. The diagnostic report needs the window, so it is not available in this case.

## What not to post

Do not post passwords, account details, complete registry exports, memory dumps or device serial numbers. If a developer needs more detail, you will be asked separately.

To report a security problem, do not open a public issue; use the private reporting described in the [security policy](../SECURITY.md).
