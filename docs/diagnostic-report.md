# Diagnostic report

A diagnostic report is a small ZIP file that PlayNice makes on your computer when you ask for it. It helps explain a problem without sharing your setups or devices. PlayNice never uploads it. You decide whether to share it.

## Make one

**Settings > Advanced > Diagnostics > Export diagnostic report…** shows what is in the report and lets you read it before saving. You can cancel at any point. It works while audio plays and while the background controller is not running, and it does not stop or change anything.

The file is named like `PlayNice-Diagnostics-20261030-140509.zip`. The date and time in the name are UTC.

## What it contains

| File | Contents |
| --- | --- |
| `report.json` | PlayNice, Qt and Windows versions; the install scope; the state of the controller and the audio engine; the number of speakers and whether each is available; buffering, drift correction and recovery settings; a summary of the last few runs (counters and error codes). |
| `recent-events.jsonl` | The latest events of the last few runs and of sleep or sign-in recovery: event names, numbers, error codes and times. |
| `manifest.json` | The list of files and what was left out. |
| `README.txt` | A short explanation. |

Devices appear as `source-1`, `speaker-1`, `speaker-2`. These names only mean something inside one report.

## What it does not contain

Saved setups and settings, device names and IDs, Bluetooth addresses, serial numbers, your user name, computer name and folders, audio recordings, registry contents, memory dumps, and the raw log files.

When a log record cannot be reduced to safe fields, it is left out and the manifest says so.

## Not anonymous

A report shows which Windows build ran PlayNice and when things happened. Read it before sharing it. If something in it should not be shared, do not attach it; describe the problem in the issue instead.

## Share it

Drag the ZIP into the optional box on the issue form. Anything attached to a public issue may be accessible to anyone, so read the report first and attach it only if you are comfortable sharing it. Please do not post raw log files or setup files. If a developer needs more, they will ask you separately.

## If PlayNice will not open

The report is made from the PlayNice window. If it cannot open, describe the problem in an issue; see [Reporting a problem](reporting-a-bug.md).
