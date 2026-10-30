# Getting started

This page takes you from download to sound on several speakers.

## 1. Download and install PlayNice

Download the installer from [Releases](https://github.com/tensorsofthewall/playnice-windows/releases) and install it for the current user (recommended). Details, checksums and upgrades are in [Installation](installation.md).

## 2. Install VB-CABLE if you need it

PlayNice receives sound from a virtual audio device. The supported one is **VB-CABLE** from VB-Audio. It is a separate product, and PlayNice does not download, install or include it.

- Get it from the official site only: <https://vb-audio.com/Cable/>.
- Follow VB-Audio's own installation instructions. They may ask for administrator rights and a restart.
- If PlayNice does not find the cable, it says so on its first screen. You can still create setups; install the cable before you start audio, then choose **Check again**.

## 3. Send sound to the cable

PlayNice never changes your Windows default audio device. You choose what goes to the cable:

1. Open **Settings > System > Sound** in Windows.
2. Under **Output**, choose **CABLE Input** to send all sound from Windows to PlayNice.
   Or open the **Volume mixer** and choose **CABLE Input** for one program only.

If your speakers stay silent later, the program is probably still playing to another device.

When all Windows sound goes to the cable, you hear it only through the speakers in your PlayNice setup.

## 4. Open PlayNice

Start it from the Start menu, or from the last page of the installer. The first screen checks for the audio source and asks you to name your first setup.

## 5. Create a setup

A **setup** is a saved list of speakers. Name it (for example "Living room") and choose **Continue to speakers**. You can rename it, copy it or make others later from **Manage setups**.

## 6. Choose an audio source

The **Audio source** card shows where PlayNice takes sound from. Choose **Change…** to pick a different source. A new setup starts on VB-CABLE when it is present.

## 7. Add speakers

Choose **Add a speaker** and pick from the list of audio outputs Windows has. Add each speaker you want to hear together. A speaker that is switched off or not connected is listed as unavailable; switch it on and refresh the list.

Bluetooth and wired outputs can be mixed in one setup. How well they work together depends on the devices.

## 8. Start playback

Save the setup, then choose **Start audio**. Play something in the program you routed to the cable. Choose **Stop audio** to stop.

Some changes, such as adding a speaker or changing a delay, take effect when you restart playback. PlayNice says so next to the control.

## 9. Adjust volume and timing

- Each speaker has a **volume slider and a mute button**. They change that speaker's volume and mute in Windows, so they also apply outside PlayNice and are not saved with the setup.
- The **Master** slider on the source card changes the volume of the cable in Windows.
- Open a speaker (the arrow on its row) to choose its **channels** (stereo, left, right, mono or swapped) and its **delay**.
- If speakers sound out of step, add delay to the faster speaker and use **Compare timing**. Adjust by ear and restart playback to apply it. PlayNice does not measure delay for you.
- **Drift correction** in Settings helps keep speakers in step over a long session. It does not line them up at the start.

## Start PlayNice at sign-in

Open **Settings** and turn on **Start PlayNice at sign-in**. It is off until you turn it on, and the installer never turns it on for you.

## If something goes wrong

See [Troubleshooting](troubleshooting.md). To report a problem, read [Reporting a problem](reporting-a-bug.md) and open an issue.
