# Settings guide

This page explains every setting in PlayNice, what it changes, and its default. It describes PlayNice 0.1.0-beta.1. Names in **bold** are the labels you see in the program. For a first walkthrough, start with [Getting started](getting-started.md).

Open Settings from the **...** (More actions) menu at the top right of the window, then **Settings…**. Settings opens in its own window and never interrupts audio; closing it changes nothing.

Contents: [General](#general-settings) · [Saved, applied and restarted](#saved-applied-and-restarted) · [Setup settings](#settings-of-the-open-setup) · [Per-speaker controls](#per-speaker-controls) · [Tray](#tray-behavior) · [Sign-in](#start-at-sign-in) · [Diagnostics](#diagnostic-export) · [Controller](#controller-shutdown) · [Defaults](#defaults-at-a-glance)

> *[Screenshot to be added: the complete Settings window. It has not been captured yet; a safe capture needs a native Windows window with no personal information visible.]*

## General settings

These belong to your Windows account on this computer, not to a setup. They take effect at once, and they never touch the audio.

| Setting | Default | What it does |
| --- | --- | --- |
| **Keep PlayNice in the system tray when the window is closed** | Off | On: closing the window hides it, and the tray icon reopens it. Off: closing the window ends the PlayNice window program. In both cases audio keeps running. See [Tray behavior](#tray-behavior). If Windows has no notification area available, this switch is unavailable and the row says so. |
| **Show a notification when something changes** | On | Shows a notification from the tray icon when an output fails or the controller is lost. It has an effect only while the tray icon is present. |
| **Start PlayNice at sign-in** | Off | See [Start at sign-in](#start-at-sign-in). |

## Saved, applied and restarted

In short:

- **Application preferences** (the **General** group) apply **immediately** and are saved at once.
- **Setup edits** (speakers, delays, channels and the **Open setup** settings) are kept only when you **save** them.
- **Engine settings** (everything that changes how audio is played) can need a **restart** of playback before they are used.

Three different things can happen to a change, and they are easy to mix up:

| Word | Meaning |
| --- | --- |
| **Saved** | The change is written to the setup on this computer. Saving does not start, stop or change playing audio. |
| **Applied** | The running audio is using the change. |
| **Restart** | Audio stops for a moment and starts again, which is how most saved changes are applied. |

How this looks in practice:

- When you edit a setup, the header shows **Unsaved changes**. Choose **Save changes** (or **Save setup** for a new setup), or **Discard changes**.
- After you save changes to a setup that is playing, the header shows **Changes saved, not applied**, and the main button becomes **Restart to apply changes**. Restarting interrupts the sound for a moment, and PlayNice may ask you to confirm.
- If the setup is not playing, **Start audio** uses the saved version.
- Choosing a different setup from the title only **opens** it. It does not start audio. To play it, choose **Switch to this setup** (or **Start audio** when nothing is playing).

What needs a restart: adding, removing or turning off a speaker, **Delay**, and every option in [Settings of the open setup](#settings-of-the-open-setup).

What takes effect while audio plays: the volume and mute of each speaker, and **Master (Windows)** (these are Windows' own volumes, see below). Switching a speaker's **Channels** is also heard right away while that speaker plays; **Save** keeps the choice for next time. If PlayNice cannot confirm how a speaker is mapped, it says so and leaves the choice for the next restart.

The **Settings** window changes the setup that is open on the main page. Changes made there are not saved until you choose **Save changes** on the main page, and the Settings window tells you when a setup has unsaved changes.

## Settings of the open setup

These live in the **Open setup** group of Settings and are saved with that setup, so each setup can have its own. They are unavailable until a setup is open. They are applied when the setup is started or restarted. All of them can be left at their defaults for normal use.

### Drift correction

**Default: off.**

Every speaker has its own clock, and no two clocks run at exactly the same speed. Over a long session, speakers can slowly slip out of step. With **Drift correction** on, PlayNice adjusts each speaker's playback rate in small steps so that it follows the source.

- It helps to keep speakers in step **over time**. It does **not** line them up at the start; use [delay](#speaker-delay-and-compare-timing) for that.
- A speaker that Windows cannot adjust this way **will not start** while drift correction is on. If a speaker will not start, turn drift correction off and try again.
- PlayNice does not promise that speakers stay perfectly in step.

### Starvation recovery

**Default: off.**

A speaker is "starved" when it runs out of audio to play, which sounds like a glitch or dropout. With **Starvation recovery** on, PlayNice plays a short silence until that speaker has a cushion of audio again, instead of letting it stutter. It may make a recovery less noticeable; it does not remove the cause.

### Priming

**Default: Automatic.**

Priming means buffering a little audio before playback starts, so that small hiccups do not cause dropouts. More priming can mean fewer interruptions, and it **adds that much delay**.

- **Automatic**: PlayNice uses 100 ms when the source is VB-CABLE and 200 ms for other sources. The line under **Priming** shows which applies.
- **Manual**: PlayNice uses exactly the number you enter under **Manual priming** (0 to 500 ms; the field starts at 200 ms). The field is available only when Priming is **Manual**.

If you hear dropouts, a larger Manual value may help; if you notice delay between sound and picture, a smaller one may help. Changing it may not fix a problem. Restart playback to apply a change.

### Optional level limiting

**Limit the level while playing: default off.**

PlayNice describes this as lowering the level and stopping audio if the peak limit would be exceeded. For ordinary listening you can leave it off. It is a **digital peak limit on the signal PlayNice handles. It is not a hearing-safety guarantee:** it does not know how loud your speakers or headphones are, or what Windows and the speakers' own volume controls are set to. Set those volumes carefully yourself. When it is on, two values apply:

- **Gain** (default **-24.0 dB**, range -120 to 0 dB). It only lowers the level; it never makes it louder. **Check this value before you turn the limit on:** the default lowers the sound a lot.
- **Peak limit** (default **0.075**, range 0.001 to 0.075). If a block of audio would exceed it, audio stops. A lower value stops audio sooner.

## Per-speaker controls

These are on the main page, for each speaker in the setup. Open a speaker with the arrow at the right of its row. A setup can have up to four speakers.

### Master and per-speaker Windows volume

PlayNice does not have a volume of its own. Its sliders are Windows' volumes:

- Each speaker's slider and mute button change that device's volume and mute **in Windows**. The same value applies in Windows Sound settings and to every other program that plays on that device, and is not saved with the setup. Moving a slider can therefore make other programs louder, quieter or silent on that speaker.
- **Master (Windows)** on the **Audio source** card is the Windows volume of the cable (**CABLE Input**), and its speaker button mutes the cable in Windows. It affects everything sent to the cable, from every program routed to it.
- The sliders work while the setup is playing. Before that, the page says to use the Windows volume.
- If the keyboard volume keys control another device (the cable is not the Windows default output), the Master row says so. This is expected when you route only one program to the cable.
- Setups saved with older software-volume settings show a notice with a **Remove old volume settings** button.

### Channel modes

For each speaker, open it and choose **Channels**:

| Mode | What the speaker plays |
| --- | --- |
| **Stereo** | Left on the left side and right on the right side. |
| **Left only** | The left channel on both sides of the device. |
| **Right only** | The right channel on both sides of the device. |
| **Mono** | Left and right mixed into one signal, on both sides. |
| **Swap sides** | The left channel on the right side and the right channel on the left. |

A common use: two separate speakers, one set to **Left only** and one to **Right only**.

### Speaker delay and compare timing

**Default: 0 ms. Range: 0 to 500 ms.**

Each speaker has a **Delay**. It holds that speaker's sound back by a number of milliseconds so that it lines up with a slower speaker. Typically a Bluetooth speaker plays later than a wired one, so you give the **wired** speaker a delay.

- You set it **by ear**. PlayNice does **not** measure the delay for you.
- Delay is applied after you save and **restart** playback. While audio plays, the row shows both the delay that is playing now and the one that is set.
- **Compare timing** (button in the **Speakers** header) shows every speaker's delay in one panel so you can adjust them side by side. On each slider the handle is the delay you are editing, the bar is the saved delay, and a ring shows the delay that is playing now (only when it differs). It is a display for adjusting by ear: it does not play a test sound and does not detect anything.
- A delay does not correct for drift over time (see [Drift correction](#drift-correction)).
- **A speaker delay does not guarantee that picture and sound will match (lip-sync) in a video.** It only moves one speaker later relative to the others; it does not know about the picture. For video, the player's own audio-delay setting may help; that has not been tested with every player.

## Tray behavior

With **Keep PlayNice in the system tray when the window is closed** on:

- Closing the window **hides** it; PlayNice shows a notice the first time (if notifications are on). The program, the controller and the audio keep running.
- The tray icon (it may be under the **^** overflow arrow) reopens the window. Its menu has **Open PlayNice**, **Start Audio**, **Stop Audio**, a list of your setups under **Profiles**, **Show Diagnostics**, **Quit GUI (audio keeps running)**, and under **Advanced**, **Shut down controller...**.
- The tooltip of the icon says whether the controller is connected and whether audio is running.

With it off, closing the window ends the window program and leaves audio running. Start PlayNice again from the Start menu to see the window.

**Quit window (audio keeps running)** in the **...** menu and **Quit GUI (audio keeps running)** in the tray menu end only the window program. Neither stops audio. If a setup has unsaved changes, PlayNice asks about them first.

If you start PlayNice while it is already running (for example from the Start menu while it is hidden in the tray), the existing window is shown; no second copy opens.

If Windows has no notification area (the tray), the switch is unavailable and closing the window ends the window program.

## Start at sign-in

**Default: off.** PlayNice never turns it on by itself, and the installer does not either.

When on, PlayNice adds two entries to your Windows account's startup list (not for other accounts, and not as a Windows service):

1. the **controller**, which resumes the setup you started last, and
2. the **PlayNice window**, started hidden so that it waits in the tray.

If the tray is not ready, PlayNice waits up to about a minute for it before showing the window instead.

- The switch shows what Windows has registered, not what was asked. If only one of the two entries exists, the row says what is missing and says **Turn this on to repair it**. If an entry points at an old location, the row says so.
- If an unrelated startup entry already uses PlayNice's entry name, the switch is unavailable and PlayNice leaves that entry unchanged.
- Windows can switch startup entries off in **Settings > Apps > Startup**. If PlayNice does not start, check there.
- Turning the switch off removes both entries and leaves other programs' entries alone.
- Resuming the last setup needs its speakers to be on and connected at sign-in.

**Test status.** The maintainer reports that one installed copy of PlayNice passed these checks on a real Windows sign-in: the window starts at sign-in, audio resumes, the window stays hidden in the tray, starting PlayNice again shows the existing window, the tray icon comes back after Windows Explorer restarts, and turning **Start PlayNice at sign-in** off works. The exact installer file and build of that copy were not recorded, and no log of the checks is kept with these documents. Not tested: a clean computer, other user accounts or more than one signed-in user, other Windows versions, and how long the tray icon takes to appear. If the window is not where you expect it, see [Troubleshooting](troubleshooting.md#the-window-is-missing-or-hidden-in-the-tray).

## Diagnostic export

**Settings > Advanced > Diagnostics > Export diagnostic report…** makes a small ZIP file for a problem report. You can read it before you save it, and nothing is uploaded. See [Diagnostic report](diagnostic-report.md) for what it holds and does not hold.

**Open folder**, next to it, opens the folder where PlayNice keeps recent run files. Those raw files are **not** the diagnostic report, are not reduced for privacy, and can contain device names and folder paths. Do not post them. It is unavailable when the folder does not exist yet.

## Controller shutdown

PlayNice has two parts: the window, and the **controller**, a background program that keeps your setups and runs the audio. Closing the window never stops audio.

**Settings > Advanced > Controller > Shut down controller…** stops any audio that is playing and ends the controller, after a confirmation. It is unavailable when the controller is not running. To use PlayNice again, open it and choose **Start controller**. To stop audio but keep the controller, use **Stop audio** on the main page instead.

## Defaults at a glance

| Setting | Where | Default |
| --- | --- | --- |
| Keep PlayNice in the system tray | General | Off |
| Show a notification when something changes | General | On |
| Start PlayNice at sign-in | General | Off |
| Drift correction | Open setup | Off |
| Starvation recovery | Open setup | Off |
| Priming | Open setup | Automatic (100 ms for VB-CABLE, 200 ms otherwise) |
| Manual priming | Open setup | 200 ms (used only in Manual) |
| Limit the level while playing | Open setup | Off |
| Gain, when limiting is on | Open setup | -24.0 dB |
| Peak limit, when limiting is on | Open setup | 0.075 |
| Delay of a speaker | Per speaker | 0 ms |
| Channels of a speaker | Per speaker | Stereo |

## What is not claimed

PlayNice does not measure delay, does not promise that speakers stay perfectly in step, does not promise that picture and sound match, and does not work with every audio device or every Bluetooth speaker. It never changes your Windows default playback device, which program uses which device, or any volume other than the volume and mute buttons you press on a speaker or on Master.
