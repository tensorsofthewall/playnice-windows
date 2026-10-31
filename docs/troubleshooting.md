# Troubleshooting

Most problems have more than one possible cause, so each section lists checks to go through in order. Stop when the problem is fixed. Names in **bold** are labels in PlayNice or Windows. If you are new to PlayNice, read [Getting started](getting-started.md) first; it explains CABLE Input, CABLE Output and the order of the steps.

Jump to: [No sound from any speaker](#no-sound-from-any-speaker) · [No sound from one speaker](#no-sound-from-one-speaker) · [Program not in Volume mixer](#an-application-is-not-listed-in-the-volume-mixer) · [VB-CABLE not detected](#vb-cable-is-not-detected) · [Wrong cable entry](#the-wrong-vb-cable-entry-is-selected) · [Silent after stopping](#windows-audio-is-silent-after-i-stop-playnice) · [Bluetooth](#a-bluetooth-speaker-is-unavailable) · [Crackling](#dropouts-or-crackling) · [Not aligned](#speakers-are-not-aligned) · [Behind video](#audio-is-delayed-compared-with-the-video) · [Window missing](#the-window-is-missing-or-hidden-in-the-tray) · [Sign-in](#audio-or-the-window-does-not-start-at-sign-in) · [Export failure](#the-diagnostic-report-cannot-be-exported)

## No sound from any speaker

Work through these in order. Each one is a separate possible cause.

1. **Is PlayNice playing?** The header should say **Playing** and the button should say **Stop audio**. If it says **Stopped**, choose **Start audio**. If an error banner is shown, read it; it says what failed.
2. **Is the controller running?** A banner saying the controller is not running means nothing can start. Choose **Start controller**.
3. **Is the program really sending its sound to the cable?** Open **Settings > System > Sound > Volume mixer** and check that the program's **Output** is **CABLE Input (VB-Audio Virtual Cable)**. If you routed nothing to the cable, PlayNice has nothing to play. (If you left the program on the Windows default device, you hear it on that device and PlayNice is not involved.)
4. **Is the program producing sound?** Check it is not paused or muted, and its own volume in the Volume mixer is up.
5. **Is the audio source the cable?** The **Audio source** card should show **CABLE Input** and **Found**. If it says **Not found**, see [VB-CABLE is not detected](#vb-cable-is-not-detected).
6. **Is the cable muted or turned down?** **Master (Windows)** on the source card is the Windows volume of the cable. Check its value and that it is not muted. Also check the cable's volume in Windows Sound settings.
7. **Are the speakers on, connected and turned up?** Each speaker's own volume and mute (on its row and in Windows Sound settings) apply. A speaker listed as unavailable cannot play.
8. **Are the speakers switched on in the setup?** Each row has a switch. A speaker switched off in the setup is silent.
9. **Did you save and restart after changing the setup?** A speaker added to a playing setup starts only after **Restart to apply changes**.

If it still fails, [export a diagnostic report](diagnostic-report.md) and [report it](reporting-a-bug.md).

## No sound from one speaker

1. **Is it listed and available?** On its row, the status should say **Available** or **Playing**. If it says unavailable or not available now, switch it on or reconnect it, then restart playback.
2. **Was it on when playback started?** A speaker that was off at the start does not join automatically. Switch it on, then choose **Restart audio** or **Restart to apply changes**.
3. **Volume and mute.** Check its slider and mute button on the row. They are the Windows volume and mute of that device, so also look at **Settings > System > Sound** and at the speaker's own volume control.
4. **Is the speaker's row switched on?** Use the switch on the row.
5. **Channels.** In the speaker's settings, **Left only** or **Right only** silences one side of a stereo speaker. Choose **Stereo** to hear everything.
6. **Is another program using the device?** Some devices cannot be used by two programs at once. Close other programs that use it.
7. **Did Windows switch it off or sleep it?** Check its state in Windows Sound settings. For Bluetooth, see [A Bluetooth speaker is unavailable](#a-bluetooth-speaker-is-unavailable).
8. If the row names a problem, choose **Choose another device…** only if you want to replace it. PlayNice never picks a replacement for you.

## An application is not listed in the Volume mixer

PlayNice does not control the Volume mixer; Windows does. A program may be missing from it for several reasons:

1. **It has not played sound yet.** Play something in it, then reopen **Settings > System > Sound > Volume mixer**. Programs usually appear after they first play sound.
2. **It is not open, or is playing nothing right now.** Start playback.
3. **Another entry has the same program.** A browser may list more than one entry. Look through the list, and look for the browser's name or icon.
4. **The program has no output choice.** Open its row with the arrow at its right. Windows versions differ in where the per-program device is chosen; older versions call the page "App volume and device preferences".
5. **The program does not follow Windows' per-program device.** A few programs choose their own audio device in their own settings (for example a media player's output setting). Choose **CABLE Input** there instead.
6. **The program was already playing when you changed the device.** Pause and resume playback, or restart the program.

If you cannot route one program, you can instead set **CABLE Input** as the Windows default playback device. Then all sound from Windows goes to PlayNice and you hear it only through the speakers in your setup, **and you hear nothing while PlayNice is stopped** (see [Windows audio is silent after I stop PlayNice](#windows-audio-is-silent-after-i-stop-playnice)). PlayNice does not do this for you.

## VB-CABLE is not detected

PlayNice detects a VB-CABLE playback device that Windows lists and that is switched on. Check, in order:

1. **Is it installed?** In **Settings > System > Sound**, look for **CABLE Input (VB-Audio Virtual Cable)** under **Output**. If it is missing, install VB-CABLE from <https://vb-audio.com/Cable/> as in [Getting started](getting-started.md#2-download-vb-cable-from-the-official-site).
2. **Did you restart Windows after installing?** VB-Audio's installer usually asks for it. Restart, then look again.
3. **Is it disabled?** In **Settings > System > Sound > More sound settings**, open the **Playback** tab, right-click an empty area, and tick **Show Disabled Devices**. If **CABLE Input** is disabled, right-click it and choose **Enable**.
4. **Did you install the right one?** Use the 64-bit setup program, run as administrator. The 32-bit one is for 32-bit Windows.
5. **Choose Check again** on the first screen, or reopen the **Audio source** card with **Change…**. PlayNice reads the list of devices when you ask.
6. **Does it show an error in Windows' Device Manager?** Under **Sound, video and game controllers**, a warning icon on the VB-Audio entry means the driver is not working. That is a VB-Audio installation problem; reinstall using VB-Audio's instructions or ask VB-Audio.

PlayNice matches the cable by the driver Windows reports, not only by its name. A different device with a similar name is not accepted.

## The wrong VB-CABLE entry is selected

- **CABLE Input** is the right one: it is the playback device that programs play to, and the one PlayNice listens to.
- **CABLE Output** is the recording end of the same cable. It is not used by PlayNice and PlayNice does not accept a cable entry as a speaker.
- If more than one entry is listed (for example **CABLE In 16ch**), choose **CABLE Input** unless you know you need another.

To change the source: on the **Audio source** card, choose **Change…**, and pick the entry that starts with **VB-CABLE:** and names **CABLE Input**. Entries labelled **Advanced, playback endpoint** are other playback devices; do not choose a speaker as the source. The speakers of the open setup are not offered as the source.

Then **Save changes** and restart playback. The source can only be changed in a setup; a running setup keeps the old source until you restart.

If you chose a normal speaker as the source by mistake, you will hear nothing from PlayNice until you choose the cable again.

## Windows audio is silent after I stop PlayNice

When you stop PlayNice, sound that a program is still sending to **CABLE Input** goes nowhere, because the cable is not a speaker. Check:

1. **In Volume mixer**, is the program's **Output** still **CABLE Input**? Set it back to **Default**, or to a speaker.
2. **Did you make CABLE Input the Windows default?** In **Settings > System > Sound**, under **Output**, choose a real speaker as the default. PlayNice never changes the default device, so this was a choice made in Windows.
3. **Restart the program** if it still does not move. Some programs only pick up the new device when restarted or when playback is paused and resumed.
4. **Is Windows muted, or the speaker off?** Check the master volume in the taskbar and the speaker itself.
5. **Closing the PlayNice window does not stop audio.** If you want audio stopped, choose **Stop audio**. If you want the whole program gone, use **Settings…** then **Shut down controller…**.

PlayNice does not change Windows routing when it stops. Stopping it does not undo the routing you set in Windows.

## A Bluetooth speaker is unavailable

Several things can make a Bluetooth speaker unavailable, and PlayNice can only report what Windows tells it:

1. **Is it on and connected?** In **Settings > Bluetooth & devices**, the speaker should say **Connected**. If it says **Paired** only, connect it.
2. **Does Windows list it as a playback device?** In **Settings > System > Sound**, it should appear under **Output**. If it appears under a different, hands-free-style name, or twice, choose the entry meant for music.
3. **Did it go to sleep or move out of range?** Many speakers disconnect after a period of silence. Wake it, reconnect it, and use the refresh button in **Add a speaker** (or choose **Check again** or restart playback).
4. **Is another device connected to it?** Some speakers allow only one connection.
5. **Was it off when playback started?** Restart playback after it is connected.
6. **Try removing and pairing again** in Windows if it will not connect at all.

PlayNice does not manage Bluetooth connections. Not every Bluetooth speaker behaves well with this use.

## Dropouts or crackling

Crackling has many possible causes. Try one change at a time and listen:

1. **Is it one speaker or all of them?** Play on one speaker alone to see which is responsible. A weak Bluetooth link is a common cause.
2. **Bluetooth distance and interference.** Move the speaker closer, and away from Wi-Fi routers and USB 3 devices.
3. **Busy computer.** Close heavy programs and listen again.
4. **Priming.** In **Settings > Open setup > Priming**, choose **Manual** and try a larger value (for example 300 ms). More priming adds delay. Restart playback to apply it. If the delay bothers you, go back down.
5. **Starvation recovery.** Turning it on may make a recovery less noticeable. It does not remove the cause.
6. **Drift correction.** Over long sessions a speaker that slowly drifts can cause glitches. Turn **Drift correction** on to test. A speaker that cannot be adjusted will not start; turn it off again if so.
7. **Other programs using the same device** can fight for it. Close them.
8. **Does it happen without PlayNice?** Play the same sound on that speaker directly in Windows. If it crackles there too, the problem is the speaker or its connection.
9. If it keeps happening, [export a diagnostic report](diagnostic-report.md) just after it happens and [report it](reporting-a-bug.md).

## Speakers are not aligned

Speakers play at slightly different times, which can sound like an echo or a smear. PlayNice does not promise that speakers are in step.

1. **Is the offset constant?** If it is the same all session, it is a start-up offset. Use the **Delay** on the **earlier** speaker (usually the wired one) until they line up. Use **Compare timing**. Adjust by ear. Save, then **Restart to apply changes**.
2. **Does the offset grow over time?** That is clock drift. Turn on **Drift correction** (see [Settings guide](settings-guide.md#drift-correction)). A device that cannot be adjusted will not start with it on.
3. **Did the offset change after a reconnect or restart?** Bluetooth delay can differ each time it connects. Re-adjust.
4. **Check the channels.** **Swap sides** or **Left only** on one speaker can sound misaligned.
5. **Check the delay is applied.** Rows show **Delay: X ms now, Y ms after a restart** when a saved delay is not yet playing. Restart playback.
6. **Different kinds of speakers** (monitor, USB, Bluetooth) have different delays. A delay of up to 500 ms is available.

## Audio is delayed compared with the video

PlayNice adds a little delay itself (priming, and any delay you set), and Bluetooth adds more. PlayNice does not promise that picture and sound will match.

1. **Is it all speakers, or one?** If only the Bluetooth speaker is late, that is usually the speaker.
2. **Lower the priming.** In **Settings > Open setup**, choose **Manual** priming with a smaller value, such as 100 ms. Less priming means more risk of dropouts. Restart playback.
3. **Remove delay you added.** Set delays to 0 ms and listen.
4. **Use the player's audio-delay setting.** Many video players can shift the sound earlier or later. This helps with a constant offset. It has not been tested with every player.
5. **Is another program in the path?** Browsers and players may have their own latency.
6. If the speakers are not in step with each other as well, see [Speakers are not aligned](#speakers-are-not-aligned).

## The window is missing or hidden in the tray

PlayNice may be running without a visible window; audio does not depend on the window.

1. **Look in the tray.** Click the **^** arrow near the clock, and look for the PlayNice icon. Click it, or right-click it and choose **Open PlayNice**.
2. **Start PlayNice from the Start menu.** If it is already running, the existing window is shown rather than a second one.
3. **Does it start hidden on purpose?** If **Start PlayNice at sign-in** is on, the window starts in the tray. This is expected. See [Start at sign-in](settings-guide.md#start-at-sign-in).
4. **Check Task Manager.** In **Details**, look for `playnice.exe`. If it is not there, the window program is not running (audio may still be). Start it from the Start menu.
5. **No tray icon?** Windows Explorer may have restarted, or the icon may be hidden under the overflow arrow. Starting PlayNice from the Start menu still opens the window. On the one installation the maintainer tested, the tray icon came back after Windows Explorer restarted; other computers were not tested.
6. **The window opened off screen?** Use **Win + arrow keys**, or right-click its taskbar button and choose **Move**.
7. **It will not open at all?** See [Reporting a problem](reporting-a-bug.md#if-playnice-will-not-start).

To see what is going on without the window: the tray icon's tooltip says whether the controller is connected and audio is running.

## Audio or the window does not start at sign-in

First decide what is missing: the **window**, the **audio**, or both. Starting at sign-in needs two entries (the controller, and the hidden window). See [Start at sign-in](settings-guide.md#start-at-sign-in).

1. **Open Settings and look at Start PlayNice at sign-in.** If the note under it says only the controller or only the window starts, or that the entry is out of date, turn the switch **on** to repair it (switch it off and on if it is already on).
2. **Is it off in Windows?** Open **Settings > Apps > Startup** and check that PlayNice is on. Windows can disable startup entries by itself.
3. **Did you move or reinstall PlayNice?** The entries store the program's location. After a move, turn the switch off and on again.
4. **Is another entry in the way?** If the switch is unavailable because an unrelated startup entry has the same name, PlayNice leaves it alone. Remove that entry in Windows if you recognise it as yours.
5. **Audio does not resume.** The controller resumes the setup you started last, if its speakers are on and connected at that moment. A Bluetooth speaker may not be connected yet when the setup starts. Start the setup from PlayNice (or the tray menu) once the speakers are connected.
6. **The window does not appear.** It is hidden in the tray on purpose. If the tray is not ready, PlayNice waits about a minute and then shows the window. See [The window is missing or hidden in the tray](#the-window-is-missing-or-hidden-in-the-tray).
7. **Slow sign-in.** A slow sign-in (for example, a busy computer) can delay the icon or the audio. Wait a minute or two before concluding it has failed.
8. **Per account.** The entries belong to one Windows account. Another account needs its own switch.
9. **Only the controller starts?** Then audio can resume but the window never opens; open PlayNice from the Start menu.

If the problem remains, note what you see after sign-in (tray icon yes or no, `playnice.exe` and `playnice-control.exe` in Task Manager yes or no) and [report it](reporting-a-bug.md#startup-and-installer-problems).

## The diagnostic report cannot be exported

Two different messages can appear:

- **The report could not be made: …** PlayNice could not gather the information. The message names the reason; try again, and include it if you report the problem.
- **The report was not saved: …** The file could not be written. Nothing else changed. Try again, or choose another folder in **Save…**.

Check:

1. **Folder permissions.** Choose a folder you can write to, such as Documents or Desktop, not a protected system folder.
2. **Disk space** and whether the file name already exists and is open elsewhere.
3. **A security product** may block saving files from PlayNice. Do not turn protection off; choose another folder, or describe the problem in the issue instead.
4. **Cancelled?** If you close the dialog, nothing is written.
5. **The window does not open at all?** Then the report cannot be made; describe the problem in an issue. See [Reporting a problem](reporting-a-bug.md#if-playnice-will-not-start).

The report works while audio plays, and also while the controller is not running (it then says the controller did not answer).

## Windows warns about the installer

The installer is not yet signed, so Windows may warn about it or block it. See [Windows warnings](installation.md#windows-warnings), and [If Smart App Control blocks PlayNice](installation.md#if-smart-app-control-blocks-playnice) if it is stopped by Smart App Control. Do not turn off Defender or SmartScreen to run it.

## Check Windows Sound settings

Open **Settings > System > Sound** to see every output and input device. **More sound settings** shows the older list with each device's state. A device that is disabled or unplugged cannot be used by PlayNice.

## Still stuck

[Report a problem](reporting-a-bug.md) with the details it asks for.
