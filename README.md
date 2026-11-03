<p align="center">
  <img src="assets/playnice-logo.svg" alt="PlayNice logo" width="120">
</p>

<h1 align="center">PlayNice</h1>

<p align="center"><strong>One audio source. Multiple speakers. On Windows 11.</strong></p>

<p align="center">
  Play the same sound through up to four speakers at once — including Bluetooth, USB, wired speakers and monitors.
</p>

<p align="center">
  <a href="https://github.com/tensorsofthewall/playnice-windows/releases/latest"><strong>Download PlayNice</strong></a>
  · <a href="docs/getting-started.md">Get started</a>
  · <a href="https://github.com/tensorsofthewall/playnice-windows/issues/new/choose">Feedback &amp; support</a>
</p>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/outputs-dark.png">
  <img src="assets/screenshots/outputs-light.png" alt="PlayNice Outputs screen showing a setup with two speakers and individual controls" width="720">
</picture>

*Screenshots use example device names.*

## What you can do

- **Play on multiple devices.** Combine up to four audio outputs, even when they use different connections.
- **Adjust each speaker independently.** Control volume and mute, play a test sound, and choose stereo, mono, left, right or swapped channels.
- **Bring speakers closer into sync.** Adjust per-speaker delays by ear and optionally enable drift correction to help keep playback aligned over time.
- **Save setups for different situations.** Switch between configurations instead of selecting every speaker again.
- **Recover from disconnects.** If a device drops out, the other speakers can keep playing while PlayNice waits for it to return. It won't silently substitute another device.
- **Keep controls within reach.** Use the system tray, and optionally launch PlayNice at sign-in. Opening PlayNice again can resume a setup that was playing when you quit.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/manage-setups-dark.png">
  <img src="assets/screenshots/manage-setups-light.png" alt="PlayNice Manage setups screen with saved speaker configurations" width="520">
</picture>

## How it works

PlayNice takes sound from a virtual audio cable and sends it to the speakers you choose:

```text
Windows or an app  →  VB-CABLE  →  PlayNice  →  Your speakers
```

You decide which programs send sound to **CABLE Input**, using Windows sound settings or the Volume Mixer. PlayNice does **not** change your default audio device or another program's routing automatically.

**VB-CABLE is a separate download.** It's donationware made by VB-Audio, not part of PlayNice. Get it from [VB-Audio's official website](https://vb-audio.com/Cable/); PlayNice guides you through the installation steps and checks whether it's working. PlayNice does not download, install or remove VB-CABLE for you.

## Get started

1. **Download and install PlayNice** from the [latest GitHub release](https://github.com/tensorsofthewall/playnice-windows/releases/latest). It runs on **64-bit Windows 11**.
2. **Install VB-CABLE** from [VB-Audio](https://vb-audio.com/Cable/) if you haven't already: extract the ZIP, run its 64-bit installer as administrator, and restart Windows.
3. **Create a speaker setup** in PlayNice and select the devices you want to hear.
4. **Send audio to CABLE Input** from Windows sound settings or the Volume Mixer, then start playback and adjust each speaker as needed.

For screenshots and detailed instructions, see the [Getting started guide](docs/getting-started.md). If you need the Microsoft Visual C++ runtime, see [Installation](docs/installation.md).

> **Windows security notice:** PlayNice is currently **unsigned**. SmartScreen may warn about it, and Smart App Control may block it. PlayNice does not recommend disabling Windows security protections to install it. Read the [installation guidance](docs/installation.md#windows-warnings) before proceeding.

## Current limitations

PlayNice aims for perceptually aligned multi-speaker playback, **not sample-perfect synchronization**. Different devices—especially Bluetooth speakers—may have different or changing delays. For now, delay adjustment is manual, automatic acoustic calibration is not available, and **video lip-sync is not guaranteed**.

Adding or removing a speaker, or changing the audio source, requires restarting audio. Channel and delay changes to an existing speaker take effect after you save them. Updates are installed manually.

## Help and feedback

- [Troubleshooting](docs/troubleshooting.md) · [FAQ](docs/faq.md) · [Settings guide](docs/settings-guide.md)
- [Report a bug or suggest a feature](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose)
- [Report a security issue privately](https://github.com/tensorsofthewall/playnice-windows/security/advisories/new)

PlayNice is **proprietary software**. This public repository hosts downloads, documentation and support, not the application's source code. See the [security policy](SECURITY.md) and [third-party notices](THIRD-PARTY-NOTICES.md). PlayNice is not affiliated with VB-Audio.
