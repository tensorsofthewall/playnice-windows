# Frequently asked questions

## What does PlayNice do?

It plays your computer's sound, or the sound of one program, on several audio outputs at the same time.

## What do I need?

64-bit Windows 11, the PlayNice installer, and the separate VB-CABLE virtual audio device. See [Getting started](getting-started.md).

## Why do I need VB-CABLE?

PlayNice needs a virtual playback device to receive the sound before it sends it to your speakers. VB-CABLE is a separate product from VB-Audio, and you install it yourself from <https://vb-audio.com/Cable/>. PlayNice does not include or install it.

## Will speakers be perfectly in step?

No promise is made. Devices differ in how long they take to play sound, and Bluetooth speakers often add noticeable delay. You can set a delay for each speaker by ear. PlayNice does not measure delay automatically.

## Will picture and sound match in a video?

PlayNice does not promise that. If you watch video, sound on a Bluetooth speaker may arrive late compared with the picture, and the player's own audio-delay setting may help. This has not been tested for every player.

## Does it work with every speaker?

No. It works with audio outputs that Windows lists as playback devices, but not every device or every Bluetooth speaker behaves well. See [Troubleshooting](troubleshooting.md) and [report](reporting-a-bug.md) anything you find.

## Does PlayNice change my Windows default audio device?

No. You choose what plays to the cable in Windows yourself. See [Getting started](getting-started.md#3-send-sound-to-the-cable).

## Why are the volume sliders tied to Windows?

Each speaker's slider and mute button change that device's volume and mute in Windows, so the same volume applies outside PlayNice. They are not saved with a setup.

## Does it start with Windows?

Only if you turn on **Start PlayNice at sign-in** in Settings. It is off by default.

## Is PlayNice open source?

No. PlayNice is proprietary software. This repository is for downloads, documentation and support, and does not contain the source code.

## Windows warns about the installer. What should I do?

The installer is not yet signed, so Windows may warn about it. Only use an installer from this repository's Releases page, and do not turn off Windows security features or add exclusions to run it. See [Installation](installation.md#windows-warnings).

## Does PlayNice send my information anywhere?

PlayNice does not upload your setups, devices or diagnostic reports. A [diagnostic report](diagnostic-report.md) is saved on your computer only when you ask for one, and you decide whether to share it.

## Where do I report a problem or ask for a feature?

[Open an issue](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose). Read [Reporting a problem](reporting-a-bug.md) first. Report security problems privately, as described in the [security policy](../SECURITY.md).
