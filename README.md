<p align="center">
  <img src="assets/playnice-logo.svg" alt="PlayNice logo: two overlapping rings, one blue and one violet" width="120">
</p>

<h1 align="center">PlayNice</h1>

<p align="center"><strong>Play audio through multiple speakers at once on Windows 11.</strong></p>

> **Status:** PlayNice is in early testing. The newest public beta, [v0.1.0-beta.2](https://github.com/tensorsofthewall/playnice-windows/releases/tag/v0.1.0-beta.2),
> is available on the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases) (marked Pre-release); [v0.1.0-beta.1](https://github.com/tensorsofthewall/playnice-windows/releases/tag/v0.1.0-beta.1) stays available. The installer is not signed.

PlayNice sends the sound of your computer, or of one program, to several audio outputs at the same time: for
example a monitor, a USB headset and a Bluetooth speaker.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/outputs-dark.png">
  <img src="assets/screenshots/outputs-light.png" alt="The PlayNice window playing one setup on two speakers, each with its own volume and mute" width="720">
</picture>

*The screenshots on this page use made-up device names.*

## What you can do

- Play audio on **several speakers together**.
- Use **Bluetooth and wired** outputs in the same setup.
- **Select an audio source**: the sound of Windows, or of one program, sent to a virtual cable.
- Save **speaker setups** and switch between them.
- Set **volume and mute** for each speaker. These change the speaker's volume in Windows.
- Choose **channels** for each speaker (stereo, left, right, mono or swapped sides).
- Adjust **timing by ear** with a delay for each speaker.
- **Start PlayNice at sign-in**, if you want it to.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/manage-setups-dark.png">
  <img src="assets/screenshots/manage-setups-light.png" alt="The Manage setups window listing three saved setups" width="520">
</picture>

## Get started

| | |
| --- | --- |
| **Download** | [v0.1.0-beta.2](https://github.com/tensorsofthewall/playnice-windows/releases/tag/v0.1.0-beta.2) (all [Releases](https://github.com/tensorsofthewall/playnice-windows/releases); betas are marked Pre-release) |
| **Install** | [Installation](docs/installation.md) |
| **First use** | [Getting started](docs/getting-started.md), a walkthrough for beginners |
| **Every setting** | [Settings guide](docs/settings-guide.md) |
| **Something wrong?** | [Troubleshooting](docs/troubleshooting.md) |
| **Report a problem** | [Open an issue](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose) and read [Reporting a problem](docs/reporting-a-bug.md) first |
| **Suggest a feature** | [Feature request](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose) |
| **Questions** | [FAQ](docs/faq.md) |

## VB-CABLE is a separate product

To send the sound of Windows (or of one program) to PlayNice, you need a virtual audio device. PlayNice works with
**VB-CABLE**, third-party donationware made by VB-Audio Software (<https://www.vb-cable.com>). It is separate from PlayNice and
VB-Audio's own terms apply to it. If it is missing, PlayNice offers **Install VB-CABLE** on its first screen: you approve VB-Audio's own
installer, restart Windows, and come back. You can also install it yourself from <https://vb-audio.com/Cable/>. When you uninstall PlayNice
you can choose to remove VB-CABLE too; keeping it is the default. The [walkthrough](docs/getting-started.md) shows every step.

## What to expect

PlayNice does not promise that speakers will be perfectly in step. Different devices, and Bluetooth in particular,
add different delays. You set a delay for each speaker by ear, and an option keeps speakers from drifting apart over
long sessions. PlayNice does not measure delay for you, does not promise that picture and sound will match in video,
and does not work with every audio device or every Bluetooth speaker. See [Troubleshooting](docs/troubleshooting.md).

PlayNice never changes your Windows default audio device, or which device a program uses, for you.

## About this repository

PlayNice is **proprietary software**. This repository is for downloads, documentation and support. It does not
contain the program's source code and is not open source.

- [Security policy](SECURITY.md)
- [Third-party notices](THIRD-PARTY-NOTICES.md)
