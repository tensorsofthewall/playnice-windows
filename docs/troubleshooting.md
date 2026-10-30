# Troubleshooting

## No sound from any speaker

1. Open **Settings > System > Sound** in Windows. Make sure the speakers are listed, switched on and not muted.
2. In PlayNice, check that the setup shows **Playing** and that each speaker is not marked as unavailable.
3. Make sure the program you listen to plays to the audio source you chose in PlayNice. PlayNice never changes the Windows default device for you.
4. Press **Refresh** in the speaker list after switching a device on or connecting it.

## One speaker is silent

- Check its volume and mute in the Windows Sound settings. PlayNice's speaker sliders change the same Windows volume and mute.
- If the speaker was off when playback started, restart playback after it is on.
- A Bluetooth speaker may need to be reconnected in Windows first.

## Crackling or dropouts

- **Starvation recovery** in Settings adds a short silence while a speaker's buffer recovers. It may make a recovery less noticeable.
- A larger **Manual** priming value buffers more audio before playback and may reduce interruptions. It adds that much delay. Restart playback to apply it.
- Move a Bluetooth speaker closer, and close other programs that use the same device.
- If it keeps happening, [report it](reporting-a-bug.md) with a diagnostic report.

## Speakers sound out of step

Use the delay on each speaker and **Compare timing**. Adjust by ear, then restart playback to apply changes. Turning on **Drift correction** keeps speakers in step over long sessions but does not line them up at the start.

## Sound does not come back after sleep

PlayNice tries to restore playback after the computer wakes. If a speaker stays silent, reconnect it in Windows and restart playback. If it happens again, see [Reporting a problem](reporting-a-bug.md) and include a diagnostic report.

## PlayNice does not start at sign-in

Open **Settings** and check **Start PlayNice at sign-in**. After a repair or move of the program, switch it off and on again to refresh the entry. Windows can disable startup entries in **Settings > Apps > Startup**.

## Windows warns about the installer

PlayNice's installer is not yet signed, so Windows may show a warning. Only install files you downloaded from this repository's releases. Do not change Windows security settings to run it.

## Check Windows Sound settings

Open **Settings > System > Sound**, then **More sound settings** to see every playback device, its state and its volume. A device that is disabled or unplugged cannot be used by PlayNice.

## Still stuck

[Report a problem](reporting-a-bug.md) with the details it asks for.
