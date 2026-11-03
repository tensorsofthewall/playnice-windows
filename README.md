<p align="center">
  <img src="assets/playnice-logo.svg" alt="PlayNice logo: two overlapping rings, one blue and one violet" width="120">
</p>

<h1 align="center">PlayNice</h1>

<p align="center"><strong>Play audio through multiple speakers at once on Windows 11.</strong></p>

> **Status:** PlayNice 0.1.0 is the first release without a beta label; it is still a young program. The newest version is on the
> [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases). The installer is not signed, so Windows may warn about it
> (see [Windows warnings](docs/installation.md#windows-warnings)).

PlayNice sends the sound of your computer, or of one program, to several audio outputs at the same time: for
example a monitor, a USB headset and a Bluetooth speaker.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/outputs-dark.png">
  <img src="assets/screenshots/outputs-light.png" alt="The PlayNice window playing one setup on two speakers, with the Send audio to PlayNice card, and a volume, mute and Test button for each speaker" width="720">
</picture>

*The screenshots on this page use made-up device names.*

## What you can do

- Play audio on **several speakers together** (up to four).
- Use **Bluetooth and wired** outputs in the same setup.
- **Select an audio source**: the sound of Windows, or of one program, sent to a virtual cable. PlayNice checks that the **VB-CABLE** virtual cable, which you install yourself from VB-Audio, is there and working, and shows guidance for the last step.
- Save **speaker setups** and switch between them.
- Set **volume and mute** for each speaker. These change the speaker's volume in Windows.
- **Test** each speaker with a short, soft sound before you rely on it, and get guided help when you **can't hear audio**.
- Choose **channels** for each speaker (stereo, left, right, mono or swapped sides), and adjust **timing by ear** with a delay for each speaker. Channel and delay changes are applied to the playing audio when you **Save**, without a restart.
- Keep playing when one speaker drops out: a speaker that disconnects (Bluetooth switched off, USB unplugged) **rejoins by itself** when it returns, while the others keep playing.
- **Open PlayNice and it starts by itself.** After **Quit PlayNice**, opening it again plays the setup that was playing; **Stop audio** is respected.
- See what is happening from the **tray icon**, whose badge shows playing, stopped, starting, warning or failed.
- **Start PlayNice at sign-in**, if you want it to.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/manage-setups-dark.png">
  <img src="assets/screenshots/manage-setups-light.png" alt="The Manage setups window listing three saved setups" width="520">
</picture>

## Get started

| | |
| --- | --- |
| **Download** | The newest installer on the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases) |
| **Install** | [Installation](docs/installation.md). The normal new installation is for all users, in `C:\Program Files\PlayNice` (Windows asks for permission once); you can choose **Install for me only** or another folder. |
| **First use** | [Getting started](docs/getting-started.md), a walkthrough for beginners |
| **Every setting** | [Settings guide](docs/settings-guide.md) |
| **Something wrong?** | [Troubleshooting](docs/troubleshooting.md) |
| **Report a problem** | [Open an issue](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose) and read [Reporting a problem](docs/reporting-a-bug.md) first |
| **Suggest a feature** | [Feature request](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose) |
| **Questions** | [FAQ](docs/faq.md) |

## VB-CABLE is a separate product

To send the sound of Windows (or of one program) to PlayNice, you need a virtual audio device. PlayNice works with
**VB-CABLE**, third-party donationware made by VB-Audio Software (<https://www.vb-cable.com>). It is separate from PlayNice and
VB-Audio's own terms apply to it. PlayNice does not include, download, install or remove it. You get it from VB-Audio: download it from
<https://vb-audio.com/Cable/>, extract the ZIP file, run `VBCABLE_Setup_x64.exe` as administrator, restart Windows, then open PlayNice again.
PlayNice shows these steps when the cable is missing, and checks that it works. When you uninstall PlayNice you can choose to delete your
PlayNice data (keeping it is the default); VB-CABLE is never touched. The [walkthrough](docs/getting-started.md) shows every step.

## What to expect

PlayNice does not promise that speakers will be perfectly in step. Different devices, and Bluetooth in particular,
add different delays, and a Bluetooth speaker can return with a different delay after it reconnects. You set a delay
for each speaker by ear, and an option keeps speakers from drifting apart over long sessions. PlayNice does not measure
delay for you, does not promise that picture and sound will match in video, and does not work with every audio device or
every Bluetooth speaker. Testing and automatic reconnection depend on what Windows reports for each device. Some features
(a speaker rejoining, live channel and delay changes, resuming after Quit) have been checked with automated tests
and fake devices, and are still being checked on physical speakers. See [Troubleshooting](docs/troubleshooting.md).

PlayNice never changes your Windows default audio device, or which device a program uses, for you.

## About this repository

PlayNice is **proprietary software**. This repository is for downloads, documentation and support. It does not
contain the program's source code and is not open source.

- [Security policy](SECURITY.md)
- [Third-party notices](THIRD-PARTY-NOTICES.md)
