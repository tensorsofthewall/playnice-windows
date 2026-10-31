# Diagnostic report

A diagnostic report is a small ZIP file that PlayNice makes on your computer when you ask for it. It helps explain a problem, and it is designed to leave out your saved setups, setup names, device names and identifiers. It is **not anonymous** (see below). PlayNice never uploads it. You decide whether to share it.

## Make one

1. Open **Settings** (the **...** menu, then **Settings…**).
2. Under **Advanced**, next to **Diagnostics**, choose **Export diagnostic report…**.
3. Read the summary. Choose **Review report** to see the exact contents, and **Hide report** to close the view.
4. Choose **Save…** and pick a folder, or **Cancel**. Nothing is written unless you choose **Save…**.

PlayNice says **Saved. Look through the file before you share it.** after it saves. You can cancel at any point. It works while audio plays and while the background controller is not running, and it does not stop or change anything.

The file is named like `PlayNice-Diagnostics-20261030-140509.zip`. The date and time in the name are UTC.

## What it contains

| File | Contents |
| --- | --- |
| `report.json` | PlayNice, Qt and Windows versions and the program's build revision; the install scope (this account, all users, or neither); the computer's architecture; the state of the controller and the audio engine; for the open setup, the number of speakers, and for each speaker whether it is switched on, whether it was available, its kind (for example Bluetooth or USB), its delay and its channel mode; the kind of audio source (for example VB-CABLE); buffering, drift correction, starvation recovery and level-limit settings; a summary of the last few runs (counters, exit codes and error codes). |
| `recent-events.jsonl` | The latest events of the last few runs and of sleep or sign-in recovery: event names, numbers, error codes and times. |
| `manifest.json` | The list of files and what was left out. |
| `README.txt` | A short explanation. |

Devices appear as `source-1`, `speaker-1`, `speaker-2`. These names only mean something inside one report.

**Audio path summary.** Since 0.1.0-beta.2 the report also has a short block of fixed words and counts: whether VB-CABLE looks absent, usable, inactive, unhealthy or waiting for a restart; whether sound from the cable is idle, present or was lost; how many speakers are set up, playing and failed; and how the last **Test** on a speaker ended (completed, failed, cancelled, timed out and so on, with Windows' error code when there was one). It does not say whether you heard the test, because PlayNice cannot know that, and it never includes a speaker's name.

## What it is designed to leave out

Saved setups and settings, setup names, device names and IDs, Bluetooth addresses, serial numbers, your user name, computer name and folders, audio recordings, registry contents, memory dumps, and the raw log files.

PlayNice also checks each value and each event record against patterns that look identifying. A record that holds such a value is dropped, and a value in `report.json` is replaced with `withheld`. The manifest says how many were removed. This is a safeguard, not a guarantee: read the report before you share it.

## Not anonymous

A report shows which Windows version ran PlayNice and PlayNice's build, what kinds of devices were in use (for example a Bluetooth speaker), the delays and channel choices of the open setup, and when things happened. Times in the file name and in `report.json` are UTC; times in the sleep and sign-in recovery records are your computer's local time. Together these can be enough to recognise a setup. If something in it should not be shared, do not attach it; describe the problem in the issue instead.

## Not the same as "Open folder"

**Settings > Advanced > Diagnostics > Open folder** opens the folder where PlayNice keeps recent run files. Those are the raw files. They are **not** reduced for privacy, they are not the diagnostic report, and they can contain device names and folder paths. Do not post them. If a developer needs one, they will ask you separately.

## Share it

Drag the ZIP into the optional box on the issue form. Anything attached to a public issue may be accessible to anyone, and a report contains system information, so read the report first and attach it only if you are comfortable sharing it. Attaching it is always optional. Please do not post raw log files or setup files. If a developer needs more, they will ask you separately.

## If PlayNice will not open

The report is made from the PlayNice window. If the window cannot open, describe the problem in an issue and give the version and Windows version as described in [Reporting a problem](reporting-a-bug.md#if-playnice-will-not-start).

## If the report cannot be saved

See [The diagnostic report cannot be exported](troubleshooting.md#the-diagnostic-report-cannot-be-exported).
